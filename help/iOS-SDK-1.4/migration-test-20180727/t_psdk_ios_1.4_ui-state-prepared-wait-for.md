---
description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-description: Before you can use most of the TVSDK player methods, the player must be in a valid status.
seo-title: Wait for a valid state
title: Wait for a valid state
uuid: 8267c7b8-d70d-4421-a2b8-1f363f31322e
index: n
internal: n
snippet: y
translate: y
---

# Wait for a valid state

The player moves through various statuses. Waiting for the player to be in the correct status ensures that the media resource has successfully loaded. If the player is not in at least the required status, many player methods throw `IllegalStateException`. The required status is usually `PTMediaPlayerStatusReady`. 
