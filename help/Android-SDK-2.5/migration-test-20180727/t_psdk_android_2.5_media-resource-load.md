---
description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-title: Load a media resource in the media player
title: Load a media resource in the media player
uuid: 10c2d637-a5ee-40c3-aa2e-dec92597644d
index: n
internal: n
snippet: y
translate: y
---

# Load a media resource in the media player


>1. Set the media player to play the new resource.
>   Replace the currently playable item by calling ` MediaPlayer.replaceCurrentResource()` and passing an existing ` MediaResource` instance. This starts the resource loading process.
>
>1. Register the ` MediaPlayerEvent.STATUS_CHANGED` event with the ` MediaPlayer` instance. In the callback, check for at least the following status values:
>    * ` MediaPlayerStatus.PREPARED`
>    * ` MediaPlayerStatus.INITIALIZED`
>    * ` MediaPlayerStatus.ERROR`
>   Through these events, the ` MediaPlayer` object notifies your application when it has successfully loaded the media resource.>
>1. When the status of the media player changes to ` INITIALIZED`, you can call ` MediaPlayer.prepareToPlay()`.
>   This status indicates that the media has been successfully loaded. The new ` MediaPlayerItem` is ready for playback. Calling ` prepareToPlay()` starts the advertising resolution and placement process, if any.>
