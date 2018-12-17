---
description: With TVSDK you can control the basic playback experience for live and video on demand (VOD). TVSDK provides methods and properties on the player instance that you can use to configure the player user interface.
seo-description: With TVSDK you can control the basic playback experience for live and video on demand (VOD). TVSDK provides methods and properties on the player instance that you can use to configure the player user interface.
seo-title: Wait for a valid state
title: Wait for a valid state
uuid: 1ab68a71-bb55-4943-a0e7-83a8d231f0c5
index: y
internal: n
snippet: y
---

# Wait for a valid state{#wait-for-a-valid-state}

With TVSDK you can control the basic playback experience for live and video on demand (VOD). TVSDK provides methods and properties on the player instance that you can use to configure the player user interface.

Before you can use most of the TVSDK player methods, the player must be in a valid state. 
The player moves through various states. Waiting for the player to be in the correct state ensures that the media resource has successfully loaded. If the player is not in at least the required state, many player methods throw `IllegalStateException`.

The required state is usually PREPARED. 
