---
description: Before you can use most of the player methods, the player must be in a valid status.
seo-description: Before you can use most of the player methods, the player must be in a valid status.
seo-title: Wait for a valid status
title: Wait for a valid status
uuid: 255defcb-6401-4a8d-b7ad-16b983ebffda
index: n
internal: n
snippet: y
translate: y
---

# Wait for a valid status

Waiting for the player to be in the correct status ensures that the media resource has successfully loaded. If the player is not in at least the required status, many player methods throw `MediaPlayerException`. The required status is usually PREPARED. When this occurs, the callback routine for `StatusChangeEventListener.onStatusChanged()` executes. 

>1. To confirm that the status is `PREPARED`, check `MediaPlayer.MediaPlayerStatus`.
