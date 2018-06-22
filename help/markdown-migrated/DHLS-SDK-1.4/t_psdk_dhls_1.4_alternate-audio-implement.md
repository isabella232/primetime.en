---
description: Late-binding audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
seo-description: Late-binding audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
seo-title: Access alternate audio tracks
title: Access alternate audio tracks
---

# Access alternate audio tracks

>1. Wait for the `codeph MediaPlayer` to be in at least the PREPARED status.
>   
>1. Listen for these events:
>* `codeph MediaPlayerItemEvent.ITEM_CREATED`: The initial list of audio tracks is available.
>* `codeph MediaPlayerItemEvent.AUDIO_UPDATED`: Audio tracks changed during playback
>   
>   
>1. Get the available audio tracks from the `codeph MediaPlayerItem` instance.
>   
>1. (Optional) Present the available tracks to the user.
>   
>1. Set the selected audio track on the `codeph MediaPlayerItem` instance.
>   
>   
