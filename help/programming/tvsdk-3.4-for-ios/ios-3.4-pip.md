---
description: PIP is a multi-window mode that allow users to play videos in plyback as well as navigate between the apps.
seo-description: PIP is a multi-window mode that allow users to play videos in plyback as well as navigate between the apps.
seo-title: Picture-in-Picture Support
title: Picture-in-Picture Support
---

# Picture-in-Picture (PiP) {#picture-in-picture}

The Picture-in-Picture playback functionality is provided by AV Foundation. 
It allows users to continue playback in a small overlay window upon loading new content in the middle or completion of playback.

## Adding Picture-in-Picture in a Custom Player {adding-picture-in-picture-custom-player}

In order to get this feature work seamlessly with TVSDK, following conditions should be met:

1. In case of VOD content only (not live), the `enableLivePreroll` property of class `PTAdMetadata` should be set to **NO**.
1. The Picture-in-Picture mode can exit using the .stop() method. In order to replace the current player item with a new player item during or after playback, use the method `replaceCurrentItemWithPlayerItem:(PTMediaPlayerItem *)item` of class PTMediaPlayer.
1. When the application goes to the background, it will continue playing in PiP (if PiP was started beforehand), provided the property `audioPlaybackInBackground` of class `PTMediaPlayer` is set to **NO**.