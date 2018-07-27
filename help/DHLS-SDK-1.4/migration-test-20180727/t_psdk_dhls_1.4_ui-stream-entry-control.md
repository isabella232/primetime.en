---
description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (DefaultMediaPlayer.LIVE_POINT).
seo-description: By default, when starting playback, VOD media starts at 0 and live media starts at the client live point (DefaultMediaPlayer.LIVE_POINT).
seo-title: Enter a stream at a specific time
title: Enter a stream at a specific time
uuid: 53986374-0770-413a-8b81-6b0730123c47
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
>   var seekableRange:TimeRange=_mediaPlayer.seekableRange; 
>   if (seekableRange.contains(desiredSeekPosition) { 
>       _mediaPlayer.seek(desiredSeekPosition); 
>   }
>   ```

>
