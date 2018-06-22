---
description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-title: Order of DRM events
title: Order of DRM events
---

# Order of DRM events

To be notified about all DRM-related events, listen for `codeph MediaPlayerEvent.DRM_METADATA`.  dispatches additional DRM events through the `codeph DRMManager` class.

