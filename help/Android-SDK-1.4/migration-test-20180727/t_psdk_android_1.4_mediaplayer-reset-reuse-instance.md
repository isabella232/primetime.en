---
description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerState.
seo-description: When you reset a MediaPlayer instance, it is returned to its uninitialized IDLE state as defined in MediaPlayerState.
seo-title: Reset or reuse a MediaPlayer instance
title: Reset or reuse a MediaPlayer instance
uuid: be95b1f1-697b-44b3-a3f2-3abd5a5d45d5
index: n
internal: n
snippet: y
translate: y
---

# Reset or reuse a MediaPlayer instance

This operation is useful in the following cases: 
* You want to reuse a ` MediaPlayer` instance but need to load a new ` MediaResource` (video content) and replace the previous instance. Resetting allows you to reuse the ` MediaPlayer` instance without the overhead of releasing resources, recreating the ` MediaPlayer`, and reallocating resources. 

* When the ` MediaPlayer` is in an ERROR state and needs to be cleared. 
  >[!IMPORTANT]
  >
  >This is the only way to recover from the ERROR state.



>1. Call ` reset` to return the ` MediaPlayer` instance to its uninitialized state:
>
>   ```
>   java>   void reset() throws IllegalStateException; 
>   
>   ```
>
>1. Use ` MediaPlayer.replaceCurrentResource` to load another ` MediaResource`.

>   >[!TIP]
>   >
>   >To clear an error, load the same ` MediaResource`. 
>
>1. When you receive the ` STATUS_CHANGED` event callback with PREPARED status, start the playback.
