---
description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-title: Order of DRM events
title: Order of DRM events
uuid: cbe7befb-2d90-4cba-85bb-41d383323643
index: n
internal: n
snippet: y
translate: y
---

# Order of DRM events

To be notified about all DRM-related events, listen for `MediaPlayerEvent.DRM_METADATA`.  <!-- PH element: phrases/primetime-sdk-name --> dispatches additional DRM events through the `DRMManager` class. 
