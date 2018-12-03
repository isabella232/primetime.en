---
description: You can complete Digital Rights Management (DRM)-specific workflows.
seo-description: You can complete Digital Rights Management (DRM)-specific workflows.
seo-title: Digital Rights Management
title: Digital Rights Management
uuid: 89f38d4f-35bc-4d20-88ce-edbc481be747
index: y
internal: n
snippet: y
---

# Digital Rights Management{#digital-rights-management}

You can complete Digital Rights Management (DRM)-specific workflows.

You can listen to the `AdobePSDK.DRMMetadataInfoEvent` event to handle DRM workflows: 

```js
... 
player.addEventListener(AdobePSDK.PSDKEventType.DRM_METADATA_INFO_AVAILABLE, onDRMMetadataInfoAvailable); 
...
```

