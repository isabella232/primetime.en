---
description: Before you can use most of the player methods, the player must be in a valid state.
seo-description: Before you can use most of the player methods, the player must be in a valid state.
seo-title: Wait for a valid state
title: Wait for a valid state
uuid: 35b7b2aa-84d7-4b2e-a2c9-230899e09166
index: n
internal: n
snippet: y
translate: y
---

# Wait for a valid state

The player moves through various states. Waiting for the player to be in the correct state ensures that the media resource has successfully loaded. If the player is not in at least the required state, many player methods throw `IllegalStateException`. The required state is usually PREPARED.
