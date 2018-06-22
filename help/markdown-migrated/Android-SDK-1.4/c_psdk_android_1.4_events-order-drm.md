---
description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-description: dispatches digital rights management (DRM) events in response to DRM-related operations such as when new DRM metadata becomes available. Your player can implement actions in response to these events.
seo-title: DRM events
title: DRM events
---

# DRM events

To be notified about all DRM-related events, listen for the following:
```java
onDRMMetadata(DRMMetadataInfo drmMetadataInfo)
```

dispatches additional DRM events through the `codeph  DRMManager` class.

The following example shows a typical progression:

```java
mediaPlayer.addEventListener(MediaPlayer.Event.DRM, 
 new MediaPlayer.DRMEventListener() { 
 @Override 
 public void onDRMMetadata(byte[] data, int length, long timestamp) {...} 
});
```
