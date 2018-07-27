---
description: To provide a smoother viewing experience, sometimes buffers the video stream. You can configure the way the player buffers.
seo-description: To provide a smoother viewing experience, sometimes buffers the video stream. You can configure the way the player buffers.
seo-title: Buffering
title: Buffering
uuid: b081b2ab-352c-41b8-b8e8-18ce7308f7ba
index: n
internal: n
snippet: y
translate: y
---

# Buffering

 <!-- PH element: phrases/primetime-sdk-name --> defines a playback buffer length of at least 30 seconds and an initial buffer time within that, before the media starts playing, of at least 5 seconds. After the application calls `play` but before playback begins,  <!-- PH element: phrases/primetime-sdk-name --> buffers the media up to the initial time to give a smooth start when it actually starts playing.
You can alter the buffer times by defining new buffering policies.
