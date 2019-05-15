---
description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-title: Wait for a valid status
title: Wait for a valid status
uuid: 7a86b4cf-f7a0-4d90-9ff2-401640a395c5
---

# Wait for a valid status {#wait-for-a-valid-status}

With TVSDK, you can control the basic playback experience for live and video on demand (VOD). TVSDK provides methods and properties on the player instance that you can use to configure the player user interface.

Before you can use most of the TVSDK player methods, the player must be in a valid status.

 Waiting for the player to be in the correct status ensures that the media resource has successfully loaded. If the player is not in at least the required status, many player methods throw `MediaPlayerException`.

The required status is usually PREPARED. When this occurs, the callback routine for `StatusChangeEventListener.onStatusChanged()` executes. 

To confirm that the status is `PREPARED`, check `MediaPlayer.MediaPlayerStatus`.