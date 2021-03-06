---
description: Late-binding audio uses PTMediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
seo-description: Late-binding audio uses PTMediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.
seo-title: Access alternate audio tracks
title: Access alternate audio tracks
uuid: 2915a74f-5ec3-457e-890d-5c79be39f37a
---

# Access alternate audio tracks {#access-alternate-audio-tracks}

Late-binding audio uses PTMediaPlayer to play a video that is specified in an M3U8 HLS playlist and that can contain several alternate audio streams.

1. Wait for the MediaPlayer to be in at least the `PTMediaPlayerStatusReady` status.
1. Listen for this event:

   notification `PTMediaPlayerItemMediaSelectionOptionsAvailable`: The initial list of audio tracks is available. 

   ```
   [[NSNotificationCenter defaultCenter] addObserver:self 
        selector:@selector(onMediaPlayerItemMediaSelectionOptionsAvailable:) 
        name:PTMediaPlayerItemMediaSelectionOptionsAvailable  
        object:self.player];
   ```

1. Get the available audio tracks from the `PTMediaPlayerItem` instance.

   ```
   - (void) onMediaPlayerItemMediaSelectionOptionsAvailable:(NSNotification *) notification { 
       NSArray* subtitlesOptions = self.player.currentItem.subtitlesOptions; 
       NSArray* audioOptions = self.player.currentItem.audioOptions; 
   }
   ```

1. (Optional) Present the available tracks to the user.
1. Set the selected audio track on the `PTMediaPlayerItem` instance.
