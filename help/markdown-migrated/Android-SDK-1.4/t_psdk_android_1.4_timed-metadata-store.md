---
description: Your application must use the appropriate TimedMetadata objects at the appropriate times.
seo-description: Your application must use the appropriate TimedMetadata objects at the appropriate times.
seo-title: Store timed metadata objects as they are dispatched
title: Store timed metadata objects as they are dispatched
---

# Store timed metadata objects as they are dispatched

During content parsing, which happens before playback,  identifies subscribed tags and notifies your application about these tags. The time that is associated with each `codeph  TimedMetadata` is the local time on the playback timeline.

Your application must complete the following tasks:

>1. Keep track of the current playback time.
>   
>1. Match the current playback time to the dispatched `codeph  TimedMetadata` objects.
>   
>   
>1. Use the `codeph  TimedMetadata` where the start time equals the current local playback time.
>   
>       
>       `codeph  TimedMetadata`
>       `codeph  ArrayList`
>       ```java
>       private List&lt;TimedMetadata&gt; _timedMetadataList = new ArrayList&lt;TimedMetadata&gt;(); 
>       ... 
>       public void onTimedMetadata(TimedMetadata timedMetadata) { 
>        ... 
>        if (timedMetadata.getName().equalsIgnoreCase("#EXT-X-CUE")) { 
>        _timedMetadataList.add(timedMetadata); 
>        } 
>        ... 
>       }
>       ```
>       
>   
>   
