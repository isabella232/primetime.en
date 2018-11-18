---
description: In some cases, you need to know whether the media content is live or VOD.
seo-description: In some cases, you need to know whether the media content is live or VOD.
seo-title: Identify whether the content is live or VOD
title: Identify whether the content is live or VOD
uuid: cf0a3b90-2b53-42e1-bed8-c74237ffdf3a
index: y
internal: n
snippet: y
---

# Identify whether the content is live or VOD{#identify-whether-the-content-is-live-or-vod}

In some cases, you need to know whether the media content is live or VOD.

1. Ensure that the player is in at least the INITIALIZED status.
1. Determine whether the `MediaPlayerItem` content is live (true) or VOD (false).

   ```
   function get isLive():Boolean;
   ```

