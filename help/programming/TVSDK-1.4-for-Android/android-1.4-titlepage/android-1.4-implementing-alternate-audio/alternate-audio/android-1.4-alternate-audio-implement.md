---
description: Late-binding audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
seo-description: Late-binding audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
seo-title: Access alternate audio tracks
title: Access alternate audio tracks
uuid: 6db686eb-63b7-4d63-9774-ccd6354b78e4
index: y
internal: n
snippet: y
---

# Access alternate audio tracks{#access-alternate-audio-tracks}

Late-binding audio uses MediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.

1. Wait for the MediaPlayer to be in at least the PREPARED state.
1. Listen for this event:

   `MediaPlayer.PlaybackEventListener.onStateChanged with state MediaPlayer.PlayerState.INITIALIZED`: The initial list of audio tracks is available. 

1. Get the available audio tracks from the `MediaPlayerItem` instance.

   `mediaPlayerItem.getAudioTracks()` 1. (Optional) Present the available tracks to the user.
1. Set the selected audio track on the `MediaPlayerItem` instance.

   `mediaPlayerItem.selectAudioTrack(audioTrack)` 