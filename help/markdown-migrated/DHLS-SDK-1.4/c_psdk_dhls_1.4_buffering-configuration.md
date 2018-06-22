---
description: To provide a smoother viewing experience, sometimes buffers the video stream. You can configure the way the player buffers.
seo-description: To provide a smoother viewing experience, sometimes buffers the video stream. You can configure the way the player buffers.
seo-title: Buffering
title: Buffering
---

# Buffering

defines a playback buffer length of at least 30 seconds and an initial buffer time within that, before the media starts playing, of at least 5 seconds. After the application calls `codeph play` but before playback begins,  buffers the media up to the initial time to give a smooth start when it actually starts playing.

You can alter the buffer times by defining new buffering policies.

