---
description: The provides APIs and sample code for handling blackout periods.
seo-description: The provides APIs and sample code for handling blackout periods.
seo-title: Implement blackout handling
title: Implement blackout handling
---

# Implement blackout handling

To implement blackout handling and provide alternate content during the blackout:

>1. Set up your app to subscribe to blackout tags in a live stream manifest. <!-- Q: The "for example" comment in the following doesn't exactly match the code. What's correct? -->
>   ```
>   - (void) createMediaPlayer:(PTMediaPlayerItem *)item 
>   { 
>       [PTSDKConfig setSubscribedTags:[NSArray arrayWithObject:&lt;INSERT-BLACKOUT-TAG&gt;]]; 
>       // For example: 
>    // [PTSDKConfig setSubscribedTags:[NSArray arrayWithObject:@"#EXT-OATCLS-SCTE35"]]; 
>   }
>   ```
>   
>   
>1. Add a notification listener for `codeph  PTTimedMetadataChangedNotification`.
>   ```
>   - (void)addobservers 
>   { 
>       [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(onMediaPlayerSubscribedTagIdentified:) 
>    name:PTTimedMetadataChangedNotification object:self.player.currentItem]; 
>   }
>   ```
>   
>   
>1. Implement a listener method for `codeph  PTTimedMetadata` objects in foreground.
>   For example:
>   ```
>   - (void)onMediaPlayerSubscribedTagIdentified:(NSNotification *)notification 
>   { 
>       NSDictionary *userInfo = [notification userInfo]; 
>       PTTimedMetadata *timedMetadata = [(PTTimedMetadata *)[userInfo objectForKey:PTTimedMetadataKey] 
>    retain]; 
>      
>    if ([timedMetadata.name isEqualToString:&lt;INSERT-BLACKOUT-TAG&gt;]) 
>       { 
>        // handle tag. For example: store it in a dictionary keyed by time to be handled when 
>    // playback time = timedMetadata time. 
>           NSNumber *timedMetadataStartTime = 
>    [NSNumber numberWithInt:(int)CMTimeGetSeconds(timedMetadata.time)]; 
>           [timedMetadataCollection setObject:timedMetadata forKey:timedMetadataStartTime]; 
>       } 
>     
>       [timedMetadata release]; 
>   }
>   ```
>   
>   
>1. Handle `codeph  TimedMetadata` objects with constant updates during playback.
>   ```
>   - (void)onMediaPlayerTimeChange:(NSNotification *)notification 
>   { 
>       @synchronized(self) 
>       { 
>           CMTimeRange seekableRange = self.player.seekableRange; 
>           if (CMTIMERANGE_IS_VALID(seekableRange)) 
>           { 
>               _currentTime = (int) CMTimeGetSeconds(self.player.currentTime); 
>               if (isnan(_currentTime)) 
>               { 
>                   _currentTime = 0; 
>               } 
>               [self handleCollectionAtTime:_currentTime]; 
>           } 
>       } 
>   }
>   ```
>   
>   
>1. Add the `codeph  PTTimedMetadata` handler to switch to alternate content and return to main content as indicated by the `codeph  PTTimedMetadata` object and its playback time.
>   ```
>   - (void)handleCollectionAtTime:(int)currentTime 
>   { 
>       NSArray *allKeys = nil; 
>       NSMutableArray * timedMetadatasToDelete = [[[NSMutableArray alloc]init]autorelease]; 
>     
>       if (!_inBlackout &amp;&amp; timedMetadataCollection) 
>       { 
>           allKeys = [timedMetadataCollection allKeys]; 
>           int count = [allKeys count]; 
>           for (int i=count-1; i&gt;-1; i--) 
>           { 
>               NSNumber *currTimedMetadataTime = allKeys[i]; 
>               PTTimedMetadata *currTimedMetadata = 
>    [timedMetadataCollection objectForKey:currTimedMetadataTime]; 
>     
>               if (currentTime == [currTimedMetadataTime integerValue] &amp;&amp;  
>                                  currTimedMetadata.name == &lt;INSERT-BLACKOUT-TAG&gt; &amp;&amp;  
>                                  [self isBlackoutStart: currTimedMetadata]) 
>               { 
>                                   PTAdMetadata *newItemAdMetadata = 
>    [self createAlternateMediaMetadata];            
>       
>               // 1. Turn off preroll on the alternate media item. 
>                   newItemAdMetadata.enableLivePreroll = NO; 
>     
>                               PTMediaPlayerItem *newItem = 
>    [[PTMediaPlayerItem alloc]initWithUrl: 
>    &lt;INSERT-ALTERNATE-STREAM-URL mediaId:&lt;INSERT-ALTERNATE-STREAM- 
>                            MEDIA-ID&gt; metadata:newItemAdMetadata]; 
>     
>     
>              // 2. Register the current (original playback item) in background. 
>                   [self.player registerCurrentItemAsBackgroundItem]; 
>                         
>              // 3. Replace the current playback item with the alternate stream. 
>                    [self.player replaceCurrentItemWithPlayerItem:newItem]; 
>                        
>              // 4. Reset observers. 
>                   [self removeObservers]; 
>                   [self addobservers]; 
>     
>              // 5. Register listener on the subscribed tags in background item. 
>                   [[NSNotificationCenter defaultCenter] addObserver:self 
>    selector:@selector(onSubscribedTagInBackground:)  
>                       name:PTTimedMetadataChangedInBackgroundNotification 
>    object:self.player.currentItem]; 
>     
>              // 6. Register listener on the error in background item. 
>                            [[NSNotificationCenter defaultCenter] 
>    addObserver:self selector:@selector(onBackgroundManifestError:)  
>                               name:PTBackgroundManifestErrorNotification   
>    object:self.player.currentItem]; 
>                 
>              // 7. Resume playback 
>                      [self.player play]; 
>     
>                       // 8. Set boolean to true to handle blackout end. 
>                     _inBlackout = YES; 
>                     break; 
>               } 
>           } 
>       } 
>       else if (_inBlackout &amp;&amp; backgroundTimedMetadataCollection) 
>       { 
>           allKeys = [backgroundTimedMetadataCollection allKeys]; 
>           int count = [allKeys count]; 
>           for (int i=count-1; i&gt;-1; i--) 
>           { 
>               NSNumber *currTimedMetadataTime = allKeys[i]; 
>               PTTimedMetadata *currTimedMetadata = 
>    [backgroundTimedMetadataCollection objectForKey:allKeys[i]]; 
>     
>               if (currentTime == ([currTimedMetadataTime integerValue] &amp;&amp;  
>    currTimedMetadata.name == &lt;INSERT-BLACKOUT-TAG&gt;  &amp;&amp;  
>    [self isBlackoutEnd:currTimedMetadata] ) 
>               {      
>                                  // 1. Come out of blackout. Unregister background item. 
>                              [self.player unregisterCurrenBackgroundItem]; 
>     
>                       PTMetadata *metadata = [self createMetadata]; 
>                       PTAdMetadata *adMetadata = 
>    (PTAdMetadata *)[currMetadata metadataForKey:PTAdResolvingMetadataKey]; 
>                             adMetadata.enableLivePreroll = NO; 
>                 
>                               PTMediaPlayerItem *item = 
>    [[[PTMediaPlayerItem alloc] initWithUrl:&lt;INSERT-ORIGINAL-URL&gt; 
>    mediaId:&lt;INSERT-ORIGINAL-MEDIAID&gt; metadata:metadata autorelease]; 
>     
>                                   // 2. Switch back to original item. 
>                       [self.player replaceCurrentItemWithPlayerItem:item]; 
>                       self.player.autoPlay = YES; 
>                       [self removeObservers]; 
>     
>                       // 3. Remove background item listener. 
>                       [[NSNotificationCenter defaultCenter] removeObserver:self 
>    name:PTTimedMetadataChangedInBackgroundNotification  
>                       object:self.player.currentItem]; 
>                         
>                                  [[NSNotificationCenter defaultCenter] removeObserver:self 
>    name:PTBackgroundManifestErrorNotification 
>                       object:self.player.currentItem]; 
>                       [self addobservers]; 
>                       [self.player play]; 
>     
>                               // 4. Update boolean to correctly maintain the current state. 
>                       _inBlackout = NO; 
>                       break; 
>               } 
>           } 
>       } 
>   }
>   ```
>   
>   
>1. Implement a listener method for `codeph  PTTimedMetadata` objects in the background.
>   ```
>   - (void)onSubscribedTagInBackground:(NSNotification *)notification 
>   { 
>       NSDictionary *userInfo = [notification userInfo]; 
>       PTTimedMetadata *timedMetadata = [(PTTimedMetadata *) 
>    [userInfo objectForKey:PTTimedMetadataKey] retain]; 
>     
>       if ([timedMetadata.name isEqualToString:&lt;INSERT-BLACKOUT-TAG&gt;]) 
>       { 
>           NSNumber *timedMetadataStartTime = 
>    [NSNumber numberWithInt:(int)CMTimeGetSeconds(timedMetadata.time)]; 
>           [backgroundTimedMetadataCollection 
>    setObject:timedMetadata forKey:timedMetadataStartTime]; 
>       } 
>     
>       [timedMetadata release]; 
>   }
>   ```
>   
>   
>1. Implement a listener method for background errors.
>   ```
>   - (void) onBackgroundManifestError:(NSNotification *)notification 
>   { 
>       NSLog (@"onBackgroundManifestError"); 
>   }
>   ```
>   
>   
>1. If the blackout range is on the DVR in the playback stream, update the non-seekable ranges.
>   ```
>   // This sample assumes that blackoutStartTimedMetadata is the PTTimedMetadata 
>   // object that indicated "blackout start", and assuming blackoutEndTimedMetadata is the 
>   // PTTimedMetadataObject that indicated "blackout end". Since in this case they are both 
>   // in DVR, both are notified to the application before playback starts. This is the right 
>   // time for the application to set this range in DVR as non-seekable range. 
>     
>   CMTime ignoreRangeStart = blackoutStartTimedMetadata.time; 
>   CMTime ignoreRangeDuration = CMTimeMakeWithSeconds(CMTimeMakeWithSeconds 
>    (CMTimeGetSeconds(blackoutEndTimedMetadata.time) -  
>    CMTimeGetSeconds(blackoutStartTimedMetadata.time)), 
>    blackoutEndTimedMetadata.time.timescale); 
>     
>   CMTimeRange ignoreRange = CMTimeRangeMake(ignoreRangeStart, ignoreRangeDuration); 
>   NSArray *ignoreRangeArray = [NSArray arrayWithObject:[NSValue valueWithCMTimeRange:ignoreRange]]; 
>   PTBlackoutMetadata *blackoutMetadata = 
>    [[PTBlackoutMetadata alloc]initWithNonSeekableRanges:ignoreRangeArray]; 
>   PTMetadata *currMetadata = self.item.metadata; 
>     
>   if (currMetadata) 
>   { 
>       [currMetadata setMetadata:blackoutMetadata forKey:PTBlackoutMetadataKey] 
>   }
>   ```
>   
>   
>   
