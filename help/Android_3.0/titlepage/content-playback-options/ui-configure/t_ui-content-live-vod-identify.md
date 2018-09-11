---
description: You might need to know whether the media content is live or video on demand (VOD).
seo-description: You might need to know whether the media content is live or video on demand (VOD).
seo-title: Identify whether the content is live or VOD
title: Identify whether the content is live or VOD
uuid: 0683e19f-956f-46dd-939e-5c07991ce0da
index: y
internal: n
snippet: y
translate: y
---

# Identify whether the content is live or VOD

You might need to know whether the media content is live or video on demand (VOD).


1. Ensure that the player is in at least the `PREPARED` state.
1. Determine whether the `MediaPlayerItem` content is live ( `true`) or VOD ( `false`).

   ```
   java   boolean isLive();
   ```

