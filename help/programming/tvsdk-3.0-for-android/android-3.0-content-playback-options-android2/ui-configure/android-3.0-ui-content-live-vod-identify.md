---
description: You might need to know whether the media content is live or video on demand (VOD).
seo-description: You might need to know whether the media content is live or video on demand (VOD).
seo-title: Identify whether the content is live or VOD
title: Identify whether the content is live or VOD
uuid: e6a66104-97fb-438a-8356-e21f94058c85
---

# Identify whether the content is live or VOD{#identify-whether-the-content-is-live-or-vod}

You might need to know whether the media content is live or video on demand (VOD).

1. Ensure that the player is in at least the `PREPARED` state.
1. Determine whether the `MediaPlayerItem` content is live ( `true`) or VOD ( `false`).

   ```java
   boolean isLive();
   ```

