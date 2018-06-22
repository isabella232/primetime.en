---
description: After a media resource is successfully loaded, creates an instance of the PTMediaPlayerItem class to provide access to that resource.
seo-description: After a media resource is successfully loaded, creates an instance of the PTMediaPlayerItem class to provide access to that resource.
seo-title: About the MediaPlayerItem class
title: About the MediaPlayerItem class
---

# About the MediaPlayerItem class

The `codeph PTMediaPlayer` resolves the media resource, loads the associated manifest file, and parses the manifest. This is the asynchronous part of the resource loading process. The `codeph PTMediaPlayerItem` instance is produced after the resource has been resolved, and this instance is a resolved version of a media resource.  provides access to the newly created `codeph PTMediaPlayerItem` instance through `codeph PTMediaPlayer.currentItem`.

>[!TIP]
>
>You must wait for the resource to be successfully loaded before accessing the media player item.
