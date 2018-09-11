---
description: Your application must use the appropriate TimedMetadata objects at the appropriate times.
seo-description: Your application must use the appropriate TimedMetadata objects at the appropriate times.
seo-title: Store timed metadata objects as they are dispatched
title: Store timed metadata objects as they are dispatched
uuid: 64317444-deac-4fc4-9981-244d68159759
index: y
internal: n
snippet: y
translate: y
---

# Store timed metadata objects as they are dispatched

Your application must use the appropriate TimedMetadata objects at the appropriate times.

During content parsing, which happens before playback, TVSDK identifies subscribed tags and notifies your application about these tags. 

>[!TIP]
>
>The time that is associated with each `TimedMetadata` is the local time on the playback timeline. 
To store timed metadata objects as they are dispatched: 

1. Keep track of the current playback time.
1. Match the current playback time to the dispatched `TimedMetadata` objects.


1. Use the `TimedMetadata` where the start time equals the current local playback time.



       `TimedMetadata``ArrayList`    
       ```
       java       private List<TimedMetadata> _timedMetadataList =  
         new ArrayList<TimedMetadata>(); 
       ... 
       public void onTimedMetadata(TimedMetadata timedMetadata) { 
           ... 
           if (timedMetadata.getName().equalsIgnoreCase("#EXT-X-CUE"))  { 
               _timedMetadataList.add(timedMetadata); 
           } 
           ... 
       }
       ```
