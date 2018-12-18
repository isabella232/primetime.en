---
description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.
seo-description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.
seo-title: DRM events
title: DRM events
uuid: f1da5b31-3fad-4bb4-8aa3-3925d5f0e123
index: y
internal: n
snippet: y
---

# DRM events{#drm-events}

TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.

 To be notified about all DRM-related events, listen for `DRMMetadataInfoEvent` for DRM events with the `MediaPlayer` object. 

|  Event  | Meaning  |
|---|---|
| `DRMMetadataInfoEvent. [DRM_METADATA_INFO_AVAILABLE](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/DRMMetadataInfoEvent.html#DRM_METADATA_INFO_AVAILABLE)`  | New DRM metadata is available.  |

