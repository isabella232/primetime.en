---
description: You should release a MediaPlayer instance and resources when you no longer need the MediaResource.
seo-description: You should release a MediaPlayer instance and resources when you no longer need the MediaResource.
seo-title: Release a MediaPlayer instance and resources
title: Release a MediaPlayer instance and resources
---

# Release a MediaPlayer instance and resources

When you release a `codeph  MediaPlayer` object, the underlying hardware resources that are associated with this `codeph  MediaPlayer` object are deallocated.

Here are some reasons to release a `codeph  MediaPlayer`:
* Holding unnecessary resources can affect performance.
* If multiple instances of the same video-codec are not supported on a device, playback failure might occur for other applications.

>1. Release the `codeph  MediaPlayer`.
>   ```
>   function release():void;
>   ```
>   
>   
>   
