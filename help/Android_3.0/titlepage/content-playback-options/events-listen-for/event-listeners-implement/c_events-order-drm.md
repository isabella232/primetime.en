---
description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-title: Order of DRM events
title: Order of DRM events
uuid: 8ba2bab4-b6e0-4687-9084-a74d0e5e3aee
index: y
internal: n
snippet: y
translate: y
---

# Order of DRM events

TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.

To be notified about all DRM-related events, listen for `MediaPlayerEvent.DRM_METADATA`. TVSDK dispatches additional DRM events through the `DRMManager` class. 
