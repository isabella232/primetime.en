---
description: If StageVideo is unavailable, and your application tries to use StageVideo, the does not issue an error. Your application can determine whether StageVideo is available by listening for the StageVideoAvailabilityEvent.
seo-description: If StageVideo is unavailable, and your application tries to use StageVideo, the does not issue an error. Your application can determine whether StageVideo is available by listening for the StageVideoAvailabilityEvent.
seo-title: Check whether StageVideo is available
title: Check whether StageVideo is available
uuid: 54468922-8bde-4daa-929b-f89607f94b60
index: n
internal: n
snippet: y
translate: y
---

# Check whether StageVideo is available

From Flash 15 and later, when hardware `StageVideo` is not available, it will fall back to software `StageVideo`. For Flash 14 and earlier, you can determine whether `StageVideo` is available. If `StageVideo` is not available, you can use `StageVideoAvailabilityEvent` to understand why it is unavailable. 

>1. Listen for `StageVideoAvailabilityEvent` to determine whether `StageVideo` is available.
>   For example:>

>    
>       ```
>       private function onStageAvailable(event:StageVideoAvailabilityEvent):void {
>           if (event.availability != StageVideoAvailability.AVAILABLE) {
>               // process the error scenario here
>           }
>       }
>       ```
>1. If `StageVideo` is not available, check `flash.media.StageVideoAvailabilityReason`.
