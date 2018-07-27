---
description: You can use TimedMetadata when the current playback time matches the start time.
seo-description: You can use TimedMetadata when the current playback time matches the start time.
seo-title: Use timed metadata
title: Use timed metadata
uuid: 7e5945b6-e43b-4632-b02e-65bc1fa1eaaf
index: n
internal: n
snippet: y
translate: y
---

# Use timed metadata

To use these saved ` TimedMetadata` objects during playback, use the saved ` ArrayList` from [ Store timed-metadata objects as they are dispatched ](t_psdk_android_1.4_timed-metadata-store.md#task_timed_metadata_store). 

>1. Run a timer and repeatedly query the current playback time.
>1. Find all of the ` TimedMetadata` objects with start times that match the current playback time.
>   You can use these objects to complete various actions.

>   >[!IMPORTANT]
>   >
>   >When checking whether the current playback time matches any ` TimedMetadata` objects, include ` shouldTriggerSubscribedTagEvent` as a condition. 

>   The timeline might change as the result of various ad behaviors. For example, one or more ad breaks might be moved from their original positions on the timeline, but ` shouldTriggerSubscribedTagEvent` ensures that the ` TimeMetadata` object's start time matches the current playback time. 
>   For example: >
>   ```
>   java>   _playbackClockEventListener = new Clock.ClockEventListener() { 
>       @Override 
>       public void onTick(String name) { 
>           getActivity().runOnUiThread(new Runnable() { 
>               @Override 
>               public void run() { 
>                             
>                   /* handle timedmetadata object list  */ 
>                   if (_mediaPlayer != null &amp;&amp; _timedMetadataList != null &amp;&amp; _timedMetadataList.size() &gt; 0) { 
>                       if (_lastKnownStatus == MediaPlayer.PlayerState.PLAYING) { 
>                           long localTime = _mediaPlayer.getLocalTime(); 
>                           Iterator&lt;TimedMetadata&gt; iterator = _timedMetadataList.iterator(); 
>                           while (iterator.hasNext()) { 
>                               TimedMetadata timedMetadata = iterator.next(); 
>                               long diff = localTime - timedMetadata.getTime(); 
>                               if (diff &gt;= 0 &amp;&amp; 
>                                   diff &lt;= PLAYBACK_CLOCK_INTERVAL &amp;&amp; 
>                                   _mediaPlayer.shouldTriggerSubscribedTagEvent()) { 
>     
>                                   // use timed metadata object 
>                               } 
>                           } 
>                       } 
>                   } 
>               } 
>           }); 
>       } 
>   }; 
>     
>   _playbackClock.addClockEventListener(_playbackClockEventListener);
>   ```

>
>1. Periodically flush stale ` TimedMetadata` instances from the list to prevent memory from continuously growing.
