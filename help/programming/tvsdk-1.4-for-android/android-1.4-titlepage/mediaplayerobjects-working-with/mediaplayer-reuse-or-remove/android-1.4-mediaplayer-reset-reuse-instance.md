---
description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerState.
seo-description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerState.
seo-title: Reset or reuse a MediaPlayer instance
title: Reset or reuse a MediaPlayer instance
uuid: 72cc4511-8ab0-44e5-b93c-b36f0321bba8
index: y
internal: n
snippet: y
---

# Reset or reuse a MediaPlayer instance{#reset-or-reuse-a-mediaplayer-instance}

When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerState.

This operation is useful in the following cases:

* You want to reuse a `MediaPlayer` instance but need to load a new `MediaResource` (video content) and replace the previous instance.

  Resetting allows you to reuse the `MediaPlayer` instance without the overhead of releasing resources, recreating the `MediaPlayer`, and reallocating resources. 

* When the `MediaPlayer` is in an ERROR state and needs to be cleared. 

  >[!IMPORTANT]
  >
  >This is the only way to recover from the ERROR state.

1. Call `reset` to return the `MediaPlayer` instance to its uninitialized state:

   ```java
   void reset() throws IllegalStateException; 
   
   ```

1. Use `MediaPlayer.replaceCurrentResource` to load another `MediaResource`.

   >[!TIP]
   >
   >To clear an error, load the same `MediaResource`.

1. When you receive the `STATUS_CHANGED` event callback with PREPARED status, start the playback.
