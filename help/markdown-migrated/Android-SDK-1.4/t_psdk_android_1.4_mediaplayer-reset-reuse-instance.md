---
description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerState.
seo-description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerState.
seo-title: Reset or reuse a MediaPlayer instance
title: Reset or reuse a MediaPlayer instance
---

# Reset or reuse a MediaPlayer instance

This operation is useful in the following cases:
* You want to reuse a `codeph  MediaPlayer` instance but need to load a new `codeph  MediaResource` (video content) and replace the previous instance.
  Resetting allows you to reuse the `codeph  MediaPlayer` instance without the overhead of releasing resources, recreating the `codeph  MediaPlayer`, and reallocating resources.
  
  
* When the `codeph  MediaPlayer` is in an ERROR state and needs to be cleared.
  >[!IMPORTANT]
  >
  >This is the only way to recover from the ERROR state.
  

>1. Call `codeph  reset` to return the `codeph  MediaPlayer` instance to its uninitialized state:
>   ```java
>   void reset() throws IllegalStateException; 
>   
>   ```
>   
>   
>1. Use `codeph  MediaPlayer.replaceCurrentResource` to load another `codeph  MediaResource`.
>   >[!TIP]
>   >
>   >To clear an error, load the same`codeph  MediaResource`.
>   
>   
>1. When you receive the `codeph  STATUS_CHANGED` event callback with PREPARED status, start the playback.
>   
>   
