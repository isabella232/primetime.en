---
description: You can complete Digital Rights Management (DRM)-specific workflows.
seo-description: You can complete Digital Rights Management (DRM)-specific workflows.
seo-title: Digital Rights Management
title: Digital Rights Management
uuid: 0c44b24b-2a57-452c-9440-101a095dffcf
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

