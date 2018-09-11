---
description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE status as defined in MediaPlayerStatus.
seo-description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE status as defined in MediaPlayerStatus.
seo-title: Reset or reuse a MediaPlayer instance
title: Reset or reuse a MediaPlayer instance
uuid: 4b733acd-c4db-49ae-8d3c-75dd8b6d9d88
index: y
internal: n
snippet: y
translate: y
---

# Reset or reuse a MediaPlayer instance

When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE status as defined in MediaPlayerStatus.

This operation is useful in the following cases: 
* You want to reuse a `MediaPlayer` instance but need to load a new `MediaResource` (video content) and replace the previous instance. Resetting allows you to reuse the `MediaPlayer` instance without the overhead of releasing resources, recreating the `MediaPlayer`, and reallocating resources. 

* When the `MediaPlayer` is in ERROR status and needs to be cleared. 
  >[!IMPORTANT]
  >
  >This is the only way to recover from the ERROR status.





1. Call `reset` to return the `MediaPlayer` instance to its uninitialized status:

   ```
   java   void reset() throws MediaPlayerException; 
   
   ```

1. Use `MediaPlayer.replaceCurrentResource()` to load another `MediaResource`.


   >[!TIP]
   >
   >To clear an error, load the same `MediaResource`. 

1. When you receive the `STATUS_CHANGED` event callback with `PREPARED` status, start the playback.
