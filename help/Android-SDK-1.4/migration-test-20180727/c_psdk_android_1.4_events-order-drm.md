---
description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-title: DRM events
title: DRM events
uuid: f4aeca23-f434-4bf9-a19e-ed0e56d1750b
index: n
internal: n
snippet: y
translate: y
---

# DRM events

To be notified about all DRM-related events, listen for the following: 
```
javaonDRMMetadata(DRMMetadataInfo drmMetadataInfo)
```

<!-- PH element: phrases/primetime-sdk-name --> dispatches additional DRM events through the ` DRMManager` class. 
The following example shows a typical progression:

```
javamediaPlayer.addEventListener(MediaPlayer.Event.DRM,  
  new MediaPlayer.DRMEventListener() { 
    @Override  
    public void onDRMMetadata(byte[] data, int length, long timestamp) {...} 
});
```
