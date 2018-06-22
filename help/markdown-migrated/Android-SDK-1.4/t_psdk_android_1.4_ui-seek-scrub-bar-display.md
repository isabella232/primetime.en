---
description: supports seeking to a specific position (time) where the stream is a sliding-window playlist, in both video on demand (VOD) and live streams.
seo-description: supports seeking to a specific position (time) where the stream is a sliding-window playlist, in both video on demand (VOD) and live streams.
seo-title: Display a seek scrub bar with the current playback position
title: Display a seek scrub bar with the current playback position
---

# Display a seek scrub bar with the current playback position

>[!IMPORTANT]
>
>Seeking in a live stream is allowed only for DVR.
>1. Set up callbacks for seeking.
>   Seeking is asynchronous, so  dispatches the following seek-related events:
>   
>* `codeph  QOSEventListener.onSeekStart` - Seek starting.
>* `codeph  QOSEventListener.onSeekComplete` - Seek successful.
>* `codeph  QOSEventListener.onOperationFailed` - Seek failed.
>   
>   
>1. Wait for the player to be in a valid state for seeking.
>   Valid states are PREPARED, COMPLETE, PAUSED, and PLAYING.
>   
>   
>   
>1. Use the native SeekBar to set `codeph  OnSeekBarChangeListener` to see when the user is scrubbing.
>   
>1. Listen for `codeph  QOSEventListener.onOperationFailed` and take appropriate actions.
>   This event passes the appropriate warning. Your application determines how to proceed, for instance, by trying the seek again or continuing playback from the previous position.
>   
>   
>   
>1. Wait for  to call the `codeph  QOSEventListener.onSeekComplete` callback.
>   
>1. Retrieve the final adjusted play position using the callback's position parameter.
>   This is important because the actual start position after the seek can be different from the requested position. Playback behavior might be affected if a seek or other repositioning ends in the middle of an ad break or skips ad breaks.
>   
>   
>   
>1. Use the position information when displaying a seek scrub bar.
>   
>   
