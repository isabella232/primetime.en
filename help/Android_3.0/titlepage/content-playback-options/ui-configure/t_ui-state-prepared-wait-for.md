---
description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-title: Wait for a valid status
title: Wait for a valid status
uuid: ad626ebd-6c03-4c5d-ad0e-381e3f50392f
index: y
internal: n
snippet: y
translate: y
---

# Wait for a valid status

Before you can use most of the TVSDK player methods, the player must be in a valid status.

Waiting for the player to be in the correct status ensures that the media resource has successfully loaded. If the player is not in at least the required status, many player methods throw `MediaPlayerException`. The required status is usually PREPARED. When this occurs, the callback routine for `StatusChangeEventListener.onStatusChanged()` executes. 

1. To confirm that the status is `PREPARED`, check `MediaPlayer.MediaPlayerStatus`.
