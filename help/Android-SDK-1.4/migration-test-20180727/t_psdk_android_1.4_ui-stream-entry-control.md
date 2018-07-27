---
description: By default, when starting playback, VOD media starts at 0 (MediaPlayer.LIVE_POINT). You can override the default behavior.
seo-description: By default, when starting playback, VOD media starts at 0 (MediaPlayer.LIVE_POINT). You can override the default behavior.
seo-title: Enter a stream at a specific time
title: Enter a stream at a specific time
uuid: d28b3012-af43-429e-893e-1fe025e7d0d4
index: n
internal: n
snippet: y
translate: y
---

# Enter a stream at a specific time


>1. Pass a position to ` MediaPlayer.prepareToPlay`.
>   <!-- PH element: phrases/primetime-sdk-name --> considers the given position to be the starting point for the asset. No seek operation is required. If the position is not inside the seekable range, <!-- PH element: phrases/primetime-sdk-name --> uses the default position.
>   For example: >
>   ```
>   java>   long desiredPostion = //TODO : choose a value; 
>   @Override 
>   public void onStateChanged(MediaPlayer.PlayerState state, MediaPlayerNotification notification) { 
>       switch (state) { 
>           case INITIALIZED: 
>               _mediaPlayer.prepareToPlay(desiredPosition); 
>               break; 
>               case PREPARING: 
>               showBufferingSpinner(); 
>               break; 
>           ... 
>       } 
>   } 
>   
>   ```

>
