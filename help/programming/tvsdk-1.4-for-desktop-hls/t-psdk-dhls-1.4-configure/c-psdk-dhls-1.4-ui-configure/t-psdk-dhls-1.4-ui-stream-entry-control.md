---
description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (DefaultMediaPlayer.LIVE_POINT).
seo-description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (DefaultMediaPlayer.LIVE_POINT).
seo-title: Enter a stream at a specific time
title: Enter a stream at a specific time
uuid: f58d908a-77b9-465f-b3a9-8fe63a249d39
index: y
internal: n
snippet: y
---

# Enter a stream at a specific time{#enter-a-stream-at-a-specific-time}

By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (DefaultMediaPlayer.LIVE_POINT).

1. Pass a position to `MediaPlayer.prepareToPlay`.

   TVSDK considers the given position to be the starting point for the asset. No seek operation is required. If the position is not inside the seekable range,  uses the default position.

   For example: 

   ```
   var seekableRange:TimeRange=_mediaPlayer.seekableRange; 
   if (seekableRange.contains(desiredSeekPosition) { 
       _mediaPlayer.seek(desiredSeekPosition); 
   }
   ```
