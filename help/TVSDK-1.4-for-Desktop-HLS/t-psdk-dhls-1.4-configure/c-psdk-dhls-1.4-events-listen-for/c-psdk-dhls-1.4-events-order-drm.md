---
description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-description: TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-title: DRM events
title: DRM events
uuid: 8b8f4d43-8ca6-4932-b226-ea42c8b1216d
index: y
internal: n
snippet: y
---

# DRM events{#drm-events}

TVSDK dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.

To be notified about all DRM-related events, listen for the following: 

```
DRMMetadataInfoEvent.DRM_METADATA_INFO_AVAILABLE
```

The following example shows a typical progression:

```
mediaPlayer.addEventListener(DRMMetadataInfoEvent.DRM_METADATA_INFO_AVAILABLE,  
                             onDRMMetadataInfoAvailable);   
private function onDRMMetadataInfoAvailable(event:DRMMetadataInfoEvent){ 
    var drmMetadataInfo:DRMMetadataInfo = event.drmMetadataInfo; 
    ... 
} 

```

