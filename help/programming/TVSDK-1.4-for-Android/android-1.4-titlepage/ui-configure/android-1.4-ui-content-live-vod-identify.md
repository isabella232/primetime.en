---
description: In some cases, you need to know whether the media content is live or VOD.
seo-description: In some cases, you need to know whether the media content is live or VOD.
seo-title: Identify whether the content is live or VOD
title: Identify whether the content is live or VOD
uuid: 07710e0d-2c9b-4c51-acd5-a2ffea966671
index: y
internal: n
snippet: y
---

# Identify whether the content is live or VOD{#identify-whether-the-content-is-live-or-vod}

In some cases, you need to know whether the media content is live or VOD.

1. Ensure that the player is in at least the PREPARED state.
1. Determine whether the `MediaPlayerItem` content is live (true) or VOD (false).

   ```java
   boolean isLive();
   ```

