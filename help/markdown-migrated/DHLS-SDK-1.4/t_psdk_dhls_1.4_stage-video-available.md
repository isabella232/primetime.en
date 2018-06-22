---
description: If StageVideo is unavailable, and your application tries to use StageVideo, the does not issue an error. Your application can determine whether StageVideo is available by listening for the StageVideoAvailabilityEvent.
seo-description: If StageVideo is unavailable, and your application tries to use StageVideo, the does not issue an error. Your application can determine whether StageVideo is available by listening for the StageVideoAvailabilityEvent.
seo-title: Check whether StageVideo is available
title: Check whether StageVideo is available
---

# Check whether StageVideo is available

From Flash 15 and later, when hardware `codeph StageVideo` is not available, it will fall back to software `codeph StageVideo`. For Flash 14 and earlier, you can determine whether `codeph StageVideo` is available. If `codeph StageVideo` is not available, you can use `codeph StageVideoAvailabilityEvent` to understand why it is unavailable.

>1. Listen for `codeph StageVideoAvailabilityEvent` to determine whether `codeph StageVideo` is available.
>   For example:
>       
>       ```
>       private function onStageAvailable(event:StageVideoAvailabilityEvent):void {
>        if (event.availability != StageVideoAvailability.AVAILABLE) {
>        // process the error scenario here
>        }
>       }
>       ```
>       
>   
>1. If `codeph StageVideo` is not available, check `codeph flash.media.StageVideoAvailabilityReason`.
>   
>   
