---
description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (MediaPlayer.LIVE_POINT). You can override the default behavior.
seo-description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (MediaPlayer.LIVE_POINT). You can override the default behavior.
seo-title: Enter a stream at a specific time
title: Enter a stream at a specific time
uuid: 9224335b-d869-4128-b0b0-cd08fe71d0cd
index: n
internal: n
snippet: y
translate: y
---

# Enter a stream at a specific time


>1. Pass a position to ` MediaPlayer.prepareToPlay`.
>   <!-- PH element: phrases/primetime-sdk-name --> considers the given position to be the starting point for the asset, and no seek operation is required. If the position is not inside the seekable range, <!-- PH element: phrases/primetime-sdk-name --> uses the default position. For more information, see[ Load a media resource in the media player ](t_psdk_android_2.5_media-resource-load.md#load-a-media-resource). 
>   For example: >
>   ```
>   java>   long desiredPostion = // TODO : choose a value; 
>   @Override 
>   public void onStatusChanged(MediaPlayerStatusChangedEvent statusChangedEvent) {   
>       switch (statusChangedEvent.getStatus()) { 
>           case INITIALIZED: 
>               _mediaPlayer.prepareToPlay(desiredPosition); 
>               break; 
>           case PREPARING: 
>               showBufferingSpinner(); 
>               break; 
>       } 
>   }
>   ```

>
