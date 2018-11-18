---
description: You can complete Digital Rights Management (DRM)-specific workflows.
seo-description: You can complete Digital Rights Management (DRM)-specific workflows.
seo-title: Digital Rights Management
title: Digital Rights Management
uuid: dd5c117e-bdbc-4dff-9471-ce97f9bfd637
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

