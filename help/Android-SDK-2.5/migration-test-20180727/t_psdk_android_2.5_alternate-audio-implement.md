---
description: Alternate audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
seo-description: Alternate audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
seo-title: Access alternate audio tracks
title: Access alternate audio tracks
uuid: 01fbd384-1c2f-44fd-8011-3146fd4901a8
index: n
internal: n
snippet: y
translate: y
---

# Access alternate audio tracks


>1. Wait for the `MediaPlayer` to be in at least the `MediaPlayerStatus.PREPARED` status.
>1. Listen for the `MediaPlayerEvent.STATUS_CHANGED` event with status `MediaPlayerStatus.PREPARED`.
>   This step means that the initial list of audio tracks is available.
>
>1. Get the available audio tracks from the `MediaPlayerItem` instance.
>
>   ```
>   java>   mediaPlayerItem.getAudioTracks()
>   ```
>
>1. (Optional) Present the available tracks to the user.
>1. Set the selected audio track on the `MediaPlayerItem` instance.
>
>   ```
>   java>   mediaPlayerItem.selectAudioTrack(audioTrack)
>   ```
>
