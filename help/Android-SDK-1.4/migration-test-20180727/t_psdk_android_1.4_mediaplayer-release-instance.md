---
description: You should release a MediaPlayer instance and resources when you no longer need the MediaResource.
seo-description: You should release a MediaPlayer instance and resources when you no longer need the MediaResource.
seo-title: Release a MediaPlayer instance and resources
title: Release a MediaPlayer instance and resources
uuid: ac51f6e4-0e3a-404c-88a5-8459568aa311
index: n
internal: n
snippet: y
translate: y
---

# Release a MediaPlayer instance and resources

When you release a ` MediaPlayer` object, the underlying hardware resources that are associated with this ` MediaPlayer` object are deallocated. 
Here are some reasons to release a MediaPlayer: 
* Holding unnecessary resources can affect performance.
* Leaving an unnecessary ` MediaPlayer` object can lead to continuous battery consumption for mobile devices.
* If multiple instances of the same video-codec are not supported on a device, playback failure might occur for other applications.


>1. Release the ` MediaPlayer`.
>
>   ```
>   java>   void release() throws IllegalStateException;
>   ```
>
