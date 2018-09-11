---
description: After a media resource is successfully loaded, TVSDKcreates an instance of the PTMediaPlayerItem class to provide access to that resource.
seo-description: After a media resource is successfully loaded, TVSDKcreates an instance of the PTMediaPlayerItem class to provide access to that resource.
seo-title: About the MediaPlayerItem class
title: About the MediaPlayerItem class
uuid: d7f885c8-28e2-457a-81c8-a1cfde1a7332
index: y
internal: n
snippet: y
translate: y
---

# About the MediaPlayerItem class

After a media resource is successfully loaded, TVSDKcreates an instance of the PTMediaPlayerItem class to provide access to that resource.

The `PTMediaPlayer` resolves the media resource, loads the associated manifest file, and parses the manifest. This is the asynchronous part of the resource loading process. The `PTMediaPlayerItem` instance is produced after the resource has been resolved, and this instance is a resolved version of a media resource. TVSDKprovides access to the newly created `PTMediaPlayerItem` instance through `PTMediaPlayer.currentItem`. 

>[!TIP]
>
>You must wait for the resource to be successfully loaded before accessing the media player item.
