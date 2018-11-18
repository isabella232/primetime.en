---
description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.
seo-description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.
seo-title: DRM events
title: DRM events
uuid: 53ee0633-bde2-4a74-b2ee-928058777acd
index: y
internal: n
snippet: y
---

# DRM events{#drm-events}

TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available.

 To be notified about all DRM-related events, register an implementation of `MediaPlayer.DRMEventListener` that includes the following callback. 

|  Event  | Meaning  |
|---|---|
| [onDRMMetadata](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.DRMEventListener.html#onDRMMetadata(DRMMetadataInfo)) `(DRMMetadataInfo drmMetadataInfo)`  | New DRM metadata is available.  |

