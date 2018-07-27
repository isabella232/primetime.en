---
description: You can add behavior to pause and play buttons.
seo-description: You can add behavior to pause and play buttons.
seo-title: Play and pause a video
title: Play and pause a video
uuid: 4ff14a44-9d92-498a-b184-59d62c5aee64
index: n
internal: n
snippet: y
translate: y
---

# Play and pause a video


>1. Create a pause/play button that does the following.
>   >1. Wait for your player to be in at least the PREPARED status.
>   >1. To start playback, call the  <!-- PH element: phrases/primetime-sdk-name --> play method:
>   >
>   >   ```
>   >   function play():void;
>   >   ```
>   >
>   >1. To pause playback, call the  <!-- PH element: phrases/primetime-sdk-name --> pause method:
>   >
>   >   ```
>   >   function pause():void;
>   >   ```
>   >
>1. Use the callback for the ` MediaPlayerStatusChangeEvent.STATUS_CHANGED` event to check for errors or to take other appropriate actions.
>   <!-- PH element: phrases/primetime-sdk-name --> calls this callback when the pause or play method is called. <!-- PH element: phrases/primetime-sdk-name --> passes information about the status change in the callback, including the new status, such as PAUSED or PLAYING.>
