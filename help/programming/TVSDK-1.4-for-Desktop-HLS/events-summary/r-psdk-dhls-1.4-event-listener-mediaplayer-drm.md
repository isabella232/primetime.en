---
description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.
seo-description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.
seo-title: DRM events
title: DRM events
uuid: d0812e9d-c1c8-409b-8ca3-91f89df22aaf
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

