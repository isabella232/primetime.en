---
description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-title: DRM events
title: DRM events
uuid: 27ea9c2e-381b-48f8-98af-6272c4be85cc
index: n
internal: n
snippet: y
translate: y
---

# DRM events

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
