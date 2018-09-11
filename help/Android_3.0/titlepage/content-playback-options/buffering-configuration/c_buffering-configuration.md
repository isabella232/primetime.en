---
description: To provide a smoother viewing experience, TVSDK sometimes buffers the video stream. You can configure how the player buffers.
seo-description: To provide a smoother viewing experience, TVSDK sometimes buffers the video stream. You can configure how the player buffers.
seo-title: Buffering
title: Buffering
uuid: 88a9edc2-f4de-4180-978e-0bc91bbd0506
index: y
internal: n
snippet: y
translate: y
---

# Buffering

To provide a smoother viewing experience, TVSDK sometimes buffers the video stream. You can configure how the player buffers.

TVSDK defines a playback buffer length of at least 30 seconds and an initial buffer time before the media starts playing, of at least 2 seconds. After the application calls `play`, but before playback begins, TVSDK buffers the media up to the initial time to give a smooth start when it actually starts playing. 

You can alter the buffer times by defining new buffering policies, and you can alter when the initial buffering occurs by using instant on. 
