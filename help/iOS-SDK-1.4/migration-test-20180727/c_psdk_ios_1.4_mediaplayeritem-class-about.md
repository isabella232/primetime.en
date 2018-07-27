---
description: After a media resource is successfully loaded, creates an instance of the PTMediaPlayerItem class to provide access to that resource.
seo-description: After a media resource is successfully loaded, creates an instance of the PTMediaPlayerItem class to provide access to that resource.
seo-title: About the MediaPlayerItem class
title: About the MediaPlayerItem class
uuid: 2a9a14d3-5735-49b9-8934-b07577fbdb9b
index: n
internal: n
snippet: y
translate: y
---

# About the MediaPlayerItem class

The `PTMediaPlayer` resolves the media resource, loads the associated manifest file, and parses the manifest. This is the asynchronous part of the resource loading process. The `PTMediaPlayerItem` instance is produced after the resource has been resolved, and this instance is a resolved version of a media resource.  <!-- PH element: phrases/primetime-sdk-name --> provides access to the newly created `PTMediaPlayerItem` instance through `PTMediaPlayer.currentItem`. 

>[!TIP]
>
>You must wait for the resource to be successfully loaded before accessing the media player item.

