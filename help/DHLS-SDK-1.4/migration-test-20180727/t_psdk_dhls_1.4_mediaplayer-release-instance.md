---
description: You should release a MediaPlayer instance and resources when you no longer need the MediaResource.
seo-description: You should release a MediaPlayer instance and resources when you no longer need the MediaResource.
seo-title: Release a MediaPlayer instance and resources
title: Release a MediaPlayer instance and resources
uuid: 8eea395b-85df-4095-9208-03e685089bd1
index: n
internal: n
snippet: y
translate: y
---

# Release a MediaPlayer instance and resources

When you release a ` MediaPlayer` object, the underlying hardware resources that are associated with this ` MediaPlayer` object are deallocated. 
Here are some reasons to release a ` MediaPlayer`: 
* Holding unnecessary resources can affect performance.
* If multiple instances of the same video-codec are not supported on a device, playback failure might occur for other applications.


>1. Release the ` MediaPlayer`.
>
>   ```
>   function release():void;
>   ```
>
