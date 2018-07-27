---
description: provides APIs and sample code for handling blackout periods.
seo-description: provides APIs and sample code for handling blackout periods.
seo-title: Implement blackout handling
title: Implement blackout handling
uuid: 148eb66a-ce3e-4346-aee8-ce5c9a97b8ac
index: n
internal: n
snippet: y
translate: y
---

# Implement blackout handling

To implement blackout handling including providing alternate content during the blackout:

>1. Set up your app to detect blackout tags in a live stream manifest.
>
>   ```
>   java>   public void createMediaPlayer { 
>       ... 
>       String[] blackoutTags = {BLACKOUTTAG}; 
>       PSDKConfig.setSubscribedTags(blackoutTags); 
>       // For example: PTSDKConfig.setSubscribedTags({"#EXT-OATCLS-SCTE35"}); 
>   }
>   ```
>
>1. Create event listeners for timed metadata events in foreground and background streams.
>
>   ```
>   java>   private MediaPlayer createMediaPlayer() { 
>       mediaPlayer.addEventListener(MediaPlayer.Event.PLAYBACK, _playbackEventListener); 
>       mediaPlayer.addEventListener(MediaPlayer.Event.BLACKOUTS, _blackoutsEventListener); 
>   }
>   ```
>
>1. Implement timed metadata event handlers for both foreground and background streams.
>   Foreground:>
>   ```
>   java>   private final MediaPlayer.PlaybackEventListener _playbackEventListener =  
>             new MediaPlayer.PlaybackEventListener() { 
>       ... 
>    
>       @override 
>       public void onTimedMetadata(TimedMetadata timedMetadata) { 
>           if (timedMetadata.getName().equal(BLACKOUTTAG) &amp;&amp;  
>               !_timedMetadataList.contains(timedMetadata)) { 
>                 _timedMetadataList.add(timedMetadata); 
>           } 
>       } 
>       ... 
>   } 
>     
>   private final MediaPlayer.BlackoutsEventListener _blackoutsEventListener =  
>     new MediaPlayer.BlackoutsEventListener() { 
>       @Override 
>       public void onTimedMetadataInBackgroundItem(TimedMetadata timedMetadata) { 
>           TimedMetadata.Type type = timedMetadata.getType(); 
>           if (type.equals(TimedMetadata.Type.TAG) &amp;&amp; _mediaPlayer.getPlaybackRange() != null  
>               &amp;&amp; _mediaPlayer.getPlaybackRange().getDuration() &gt; 0) { 
>               if (!_timedMetadataList.contains(timedMetadata) &amp;&amp; isBlackoutMetadata(timedMetadata)) { 
>                   _timedMetadataList.add(timedMetadata); 
>               } 
>           } 
>       } 
>    
>       @Override 
>       public void onBackgroundManifestFailed() { 
>           ... 
>       } 
>   }; 
>   
>   ```
>
>1. Handle ` TimedMetadata` objects when ` MediaPlayer` time runs.
>
>   ```
>   java>   _playbackClockEventListener = new Clock.ClockEventListener() { 
>       @Override 
>       public void onTick(String name) { 
>           getActivity().runOnUiThread(new Runnable() { 
>               @Override 
>               public void run() { 
>                   /* handle timedmetadata object list  */ 
>                   if (_mediaPlayer != null &amp;&amp; _timedMetadataList != null  
>                       &amp;&amp; _timedMetadataList.size() &gt; 0) { 
>                       if (_lastKnownStatus == MediaPlayer.PlayerState.PLAYING) { 
>                           long localTime = _mediaPlayer.getLocalTime(); 
>                           handleTimedMetadataList(localTime);      
>                       } 
>                   } 
>               }                        
>           }); 
>       } 
>   };
>   ```
>
>1. Create methods for switching content at the start and end of the blackout period.
>
>   ```
>   java>   private void handleTimedMetadataList(long currentTime) { 
>       for (int i = 0; i &lt; _timedMetadataList.size(); i++) { 
>           TimedMetadata timedMetadata = _timedMetadataList.get(i); 
>           long diff = localTime - timedMetadata.getTime(); 
>           if (!_timedMetadataDispatchedList.contains(timedMetadata) 
>               &amp;&amp; diff &gt;= 0 
>               &amp;&amp; diff &lt;= PLAYBACK_CLOCK_INTERVAL 
>               &amp;&amp; _mediaPlayer.shouldTriggerSubscribedTagEvent()) { 
>                   // switch to blackout content 
>               if (!_inBlackout &amp;&amp; isBlackoutStartTimedMetadata(timedMetadata)) { 
>                   MediaResource blackoutMediaResource = createBlackoutMediaResource(timedMetadata); 
>                         
>                   //1. register current item as background item 
>                   _mediaPlayer.registerCurrentItemAsBackgroundItem(); 
>     
>                   //2. replace current item with blackout item 
>                   _mediaPlayer.replaceCurrentItem(blackoutMediaResource); 
>     
>                   //3. update qos metrics 
>                   _mediaQosProvider.updateMetrics(_mediaPlayer); 
>     
>                   //4. maintain state 
>                   _inBlackout = true; 
>                   resetTimedMetada(); 
>     
>                   break; 
>               } 
>               // switch back to main content 
>               else if (_inBlackout &amp;&amp; isBlackoutEndTimedMetadata(timedMetadata)) { 
>                   //1. register current item as background item 
>                   _mediaPlayer.unregisterCurrentBackgroundItem(); 
>     
>                   //2. replace current item with blackout item 
>                   _mediaPlayer.replaceCurrentItem(_oldMediaResource); 
>     
>                   //3. update qos metrics 
>                   _mediaQosProvider.updateMetrics(_mediaPlayer); 
>     
>                   //4. maintain state 
>                   _inBlackout = false; 
>                   resetTimedMetada(); 
>     
>                   break; 
>               } 
>           } 
>       } 
>   }
>   ```
>
>1. Update nonseekable ranges if the blackout range is in DVR on the playback stream.
>
>   ```
>   java>   // prepare and update blackout nonSeekable ranges 
>     
>   List&lt;TimeRange&gt; blackoutRanges = prepareBlackoutRanges(_timedMetadataList); 
>   if (blackoutRanges != null &amp;&amp; blackoutRanges.size() &gt; 0) { 
>       int size = blackoutRanges.size(); 
>       TimeRange[] blackoutRangesArray = blackoutRanges.toArray(new TimeRange[size]); 
>       BlackoutMetadata blackoutMetadata = new BlackoutMetadata(blackoutRangesArray); 
>       updateBlackoutMetadata(blackoutMetadata); 
>   } 
>     
>   // function to update blackout metadata 
>   private void updateBlackoutMetadata(BlackoutMetadata blackoutMetadata) { 
>       MediaPlayerItem currentItem = _mediaPlayer.getCurrentItem(); 
>       if (currentItem != null) { 
>           Metadata metadata = currentItem.getResource().getMetadata(); 
>           if (metadata != null) { 
>               MetadataNode metadataNode = ((MetadataNode) metadata); 
>               metadataNode.setNode(DefaultMetadataKeys.BLACKOUT_METADATA_KEY.getValue(),  
>                                    blackoutMetadata); 
>     
>               for (int i = 0; i &lt; blackoutMetadata.getNonSeekableRanges().length; i++) { 
>                   TimeRange timeRange = blackoutMetadata.getNonSeekableRanges()[i]; 
>               } 
>           } 
>       } 
>   }
>   ```

>   >[!NOTE]
>   >
>   >Currently for multiple bit-rate live streams, occasionally the adjustable bit-rate (ABR) profiles can get out of sync. This causes duplicate ` timedMetadata` objects for the same subscribed tag. To avoid incorrect non-seekable calculations, it is highly recommended to check for overlapping non-seekable ranges after your calculations, such as in the following example: 
>
>   ```
>   java>   List&lt;TimeRange&gt; rangesToRemove = new ArrayList&lt;TimeRange&gt;(); 
>     
>   for (int i = 0; i &lt; nonSeekableRanges.size() - 1; i++) { 
>       TimeRange range1 = nonSeekableRanges.get(i); 
>       TimeRange range2 = nonSeekableRanges.get(i + 1); 
>       if (range1.contains(range2.getBegin()) &amp;&amp; !rangesToRemove.contains(range2)) { 
>          rangesToRemove.add(range2); 
>       } else if (range2.contains(range1.getBegin()) &amp;&amp; !rangesToRemove.contains(range1)) { 
>          rangesToRemove.add(range1); 
>      } 
>   } 
>       
>   if (nonSeekableRanges.size() &gt; 0 &amp;&amp; rangesToRemove.size() &gt; 0) { 
>       nonSeekableRanges.removeAll(rangesToRemove); 
>       for (int i = 0; i &lt; rangesToRemove.size(); i++) { 
>           TimeRange range = rangesToRemove.get(i); 
>       } 
>   } 
>     
>   if (nonSeekableRanges.size() &gt; 0 &amp;&amp; rangesToRemove.size() &gt; 0) { 
>       nonSeekableRanges.removeAll(rangesToRemove); 
>   }
>   ```
>
