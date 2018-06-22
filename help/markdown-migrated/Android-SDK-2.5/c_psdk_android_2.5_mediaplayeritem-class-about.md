---
description: After you successfully load the MediaResource object, creates an instance of the MediaPlayerItem class to provide access to that resource.
seo-description: After you successfully load the MediaResource object, creates an instance of the MediaPlayerItem class to provide access to that resource.
seo-title: About the MediaPlayerItem class
title: About the MediaPlayerItem class
---

# About the MediaPlayerItem class

The `codeph MediaResource` represents a request that is issued by the application layer to the `codeph MediaPlayer` instance to load content.

The `codeph MediaPlayer` resolves the media resource, loads the associated manifest file, and parses the manifest. This is the asynchronous part of the resource loading process. The `codeph MediaPlayerItem` instance is produced after the resource has been resolved, and this instance is a resolved version of a `codeph MediaResource`.  provides access to the newly created `codeph MediaPlayerItem` instance through `codeph MediaPlayer.CurrentItem`.

>[!TIP]
>
>You must wait for the resource to be successfully loaded before accessing the media player item.
