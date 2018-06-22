---
description: 
seo-description: 
seo-title: Mark ranges
title: Mark ranges
---

# Mark ranges

To implement the`codeph  PTTimeRangeCollection` and mark ranges of content as ads:
>1. Prepare the `codeph  PTTimeRangeCollection`.
>   
>1. Set the type of the `codeph  PTTimeRangeCollection` to `codeph  PTTimeRangeCollectionTypeMarkRanges`.
>   This step notifies  that the custom ranges must be treated like ads.
>   
>   ```
>   #define PSDK_TIMESCALE 100000 
>         
>   NSArray *ranges =  @[ 
>    [PTReplacementRange 
>    replacementRangeWithRange:CMTimeRangeMake(CMTimeMakeWithSeconds 
>    (0, PSDK_TIMESCALE),CMTimeMakeWithSeconds(60, AD_TIMESCALE))], 
>    [PTReplacementRange 
>    replacementRangeWithRange:CMTimeRangeMake(CMTimeMakeWithSeconds 
>    (120, PSDK_TIMESCALE),CMTimeMakeWithSeconds(60, AD_TIMESCALE))] 
>   ]; 
>         
>   PTTimeRangeCollection *timeRangeCollection = 
>    [[PTTimeRangeCollection alloc] initWithRanges:ranges 
>    type:PTTimeRangeCollectionTypeMarkRanges];
>   ```
>   
>   
>1. Create the `codeph  PTAdMetadata` and set the `codeph  PTTimeRangeCollection`.
>   ```
>   // Create the PTPlayerItem metadata 
>   PTMetadata *metadata = [[PTMetadata alloc] init]; 
>     
>   // Create the Ad metadata 
>   PTAuditudeMetadata *adMetadata = [[PTAuditudeMetadata alloc] init]; 
>   adMetadata.timeRangeCollection = timerangeCollection; 
>     
>   //Set Ad metadata 
>   [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey]; 
>     
>   //Create PTMediaPlayerItem 
>   PTMediaPlayerItem *playerItem = [[[PTMediaPlayerItem alloc] initWithUrl:mediaUrl 
>                                                                   mediaId:mediaId 
>                                                                  metadata:metadata];
>   ```
>   
>   
>1. Create the player and start playback.
>   ```
>   //Create PTMediaPlayer using the created PTMediaPlayer 
>   PTMediaPlayer *player = [PTMediaPlayer playerWithMediaPlayerItem:playerItem]; 
>     
>   //Add player to the player UIView 
>   [self.playerView addSubview:(UIView *)player.view]; 
>     
>   //Start playback 
>   [player play];
>   ```
>   
>   
>   
