---
description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (MediaPlayer.LIVE_POINT). You can override the default behavior.
seo-description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (MediaPlayer.LIVE_POINT). You can override the default behavior.
seo-title: Enter a stream at a specific time
title: Enter a stream at a specific time
uuid: 6342dbf4-9e02-4bcc-a390-9e2c3099a372
index: y
internal: n
snippet: y
---

# Enter a stream at a specific time{#enter-a-stream-at-a-specific-time}

By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (MediaPlayer.LIVE_POINT). You can override the default behavior.

1. Pass a position to `MediaPlayer.prepareToPlay`.

   TVSDK considers the given position to be the starting point for the asset, and no seek operation is required. If the position is not inside the seekable range, TVSDK uses the default position. For more information, see [Load a media resource in the media player](../../content-playback-options/mediaplayer-initialize-for-video/t-psdk-android-2.5-media-resource-load.md#load-a-media-resource).

   For example: 

   ```java
   long desiredPostion = // TODO : choose a value; 
   @Override 
   public void onStatusChanged(MediaPlayerStatusChangedEvent statusChangedEvent) {   
       switch (statusChangedEvent.getStatus()) { 
           case INITIALIZED: 
               _mediaPlayer.prepareToPlay(desiredPosition); 
               break; 
           case PREPARING: 
               showBufferingSpinner(); 
               break; 
       } 
   }
   ```

