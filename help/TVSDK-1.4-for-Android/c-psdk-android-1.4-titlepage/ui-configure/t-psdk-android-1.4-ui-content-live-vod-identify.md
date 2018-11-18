---
description: In some cases, you need to know whether the media content is live or VOD.
seo-description: In some cases, you need to know whether the media content is live or VOD.
seo-title: Identify whether the content is live or VOD
title: Identify whether the content is live or VOD
uuid: 9a98d28f-9731-48c4-a753-0dbf462e4568
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

