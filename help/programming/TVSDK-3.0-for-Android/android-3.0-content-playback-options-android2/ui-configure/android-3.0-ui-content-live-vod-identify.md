---
description: You might need to know whether the media content is live or video on demand (VOD).
seo-description: You might need to know whether the media content is live or video on demand (VOD).
seo-title: Identify whether the content is live or VOD
title: Identify whether the content is live or VOD
uuid: 83639faf-bd97-4f16-b28d-5bb62edd7413
index: y
internal: n
snippet: y
---

# Identify whether the content is live or VOD{#identify-whether-the-content-is-live-or-vod}

You might need to know whether the media content is live or video on demand (VOD).

1. Ensure that the player is in at least the `PREPARED` state.
1. Determine whether the `MediaPlayerItem` content is live ( `true`) or VOD ( `false`).

   ```java
   boolean isLive();
   ```

