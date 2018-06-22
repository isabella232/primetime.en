---
description: supports seeking to a specific position (time) where the stream is a sliding-window playlist, in video on demand (VOD) and live streams.
seo-description: supports seeking to a specific position (time) where the stream is a sliding-window playlist, in video on demand (VOD) and live streams.
seo-title: Display a seek scrub bar with the current playback position
title: Display a seek scrub bar with the current playback position
---

# Display a seek scrub bar with the current playback position

>[!TIP]
>
>Seeking in a live stream is allowed only for DVR.
>1. Set up callbacks for seeking.
>   Seeking is asynchronous, so  dispatches the following seek-related events:
>   
>* `codeph  MediaPlayerEvent.SEEK_BEGIN`, where the seek starts.
>* `codeph  MediaPlayerEvent.SEEK_END`, where the seek is successful.
>* `codeph  MediaPlayerEvent.OPERATION_FAILED`, where the seek has failed.
>   
>   
>1. Wait for the player to be in a valid status for seeking.
>   The valid statuses are PREPARED, COMPLETE, PAUSED, and PLAYING.
>   
>1. Use the native `codeph  SeekBar` to set `codeph  OnSeekBarChangeListener`, which determines when the user is scrubbing.
>   
>1. Pass the requested seek position (milliseconds) to the `codeph  MediaPlayer.seek` method.
>   
>   ```java
>   void seek(long position) throws MediaPlayerException;
>   ```
>   
>   You can seek only in the asset’s seekable duration. For video on demand, that is from 0 through the asset's duration.
>   
>   >[!TIP]
>   >
>   >This step moves the play head to a new position in the stream, but the final computed position might differ from the specified seek position.
>   
>   
>1. Listen for `codeph  MediaPlayerEvent.OPERATION_FAILED` and take appropriate actions.
>   This event passes the appropriate warning. Your application determines how to proceed, and the options include trying the seek again or continuing playback from the previous position.
>   
>   
>   
>1. Wait for  to call the `codeph  MediaPlayerEvent.SEEK_END` callback.
>   
>1. Retrieve the final adjusted play position using the callback's position parameter.
>   This is important because the actual start position after the seek can be different from the requested position. Rules, including playback behavior is affected if a seek or other repositioning ends in the middle of an ad break or skips ad breaks, might apply.
>   
>   
>   
>1. Use the position information when displaying a seek scrub bar.
>   
>   
