---
description: Your application must use the appropriate TimedMetadata objects at the appropriate times.
seo-description: Your application must use the appropriate TimedMetadata objects at the appropriate times.
seo-title: Store timed metadata objects as they are dispatched
title: Store timed metadata objects as they are dispatched
uuid: 7bb7dbfa-a855-4027-8b59-eca6dd8873ad
index: n
internal: n
snippet: y
translate: y
---

# Store timed metadata objects as they are dispatched

During content parsing, which happens before playback,  <!-- PH element: phrases/primetime-sdk-name --> identifies subscribed tags and notifies your application about these tags.

>[!TIP]
>
>The time that is associated with each ` TimedMetadata` is the local time on the playback timeline. 

To store timed metadata objects as they are dispatched:

>1. Keep track of the current playback time.
>1. Match the current playback time to the dispatched ` TimedMetadata` objects.
>
>1. Use the ` TimedMetadata` where the start time equals the current local playback time.
>

>       ` TimedMetadata`` ArrayList`>    
>       ```
>       java>       private List&lt;TimedMetadata&gt; _timedMetadataList =  
>         new ArrayList&lt;TimedMetadata&gt;(); 
>       ... 
>       public void onTimedMetadata(TimedMetadata timedMetadata) { 
>           ... 
>           if (timedMetadata.getName().equalsIgnoreCase("#EXT-X-CUE"))  { 
>               _timedMetadataList.add(timedMetadata); 
>           } 
>           ... 
>       }
>       ```
