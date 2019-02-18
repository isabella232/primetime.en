---
description: You can complete Digital Rights Management (DRM)-specific workflows.
seo-description: You can complete Digital Rights Management (DRM)-specific workflows.
seo-title: Digital Rights Management
title: Digital Rights Management
uuid: 011605c7-50c4-4ad5-9961-8cd92d0e6fd8
---

# Overview {#digital-rights-management}

You can complete Digital Rights Management (DRM)-specific workflows.

You can listen to the `AdobePSDK.DRMMetadataInfoEvent` event to handle DRM workflows: 

```js
... 
player.addEventListener(AdobePSDK.PSDKEventType.DRM_METADATA_INFO_AVAILABLE, onDRMMetadataInfoAvailable); 
...
```