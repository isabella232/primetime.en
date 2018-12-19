---
description: You should release a MediaPlayer instance and resources when you no longer need the MediaResource.
seo-description: You should release a MediaPlayer instance and resources when you no longer need the MediaResource.
seo-title: Release a MediaPlayer instance and resources
title: Release a MediaPlayer instance and resources
uuid: dd3fb5f2-8656-4f85-bdf1-ff2f14b9c716
index: y
internal: n
snippet: y
---

# Release a MediaPlayer instance and resources{#release-a-mediaplayer-instance-and-resources}

You should release a MediaPlayer instance and resources when you no longer need the MediaResource.

When you release a `MediaPlayer` object, the underlying hardware resources that are associated with this `MediaPlayer` object are deallocated.

Here are some reasons to release a MediaPlayer:

* Holding unnecessary resources can affect performance. 
* Leaving an unnecessary `MediaPlayer` object can lead to continuous battery consumption for mobile devices. 
* If multiple instances of the same video-codec are not supported on a device, playback failure might occur for other applications.

1. Release the `MediaPlayer`.

   ```java
   void release() throws IllegalStateException;
   ```

>After the `MediaPlayer` instance is released, you can no longer use it. If any method of the `MediaPlayer` interface is called after it is released, an `IllegalStateException` is thrown. 