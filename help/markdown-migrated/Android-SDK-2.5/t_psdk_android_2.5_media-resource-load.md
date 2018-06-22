---
description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-title: Load a media resource in the media player
title: Load a media resource in the media player
---

# Load a media resource in the media player

>1. Set the media player to play the new resource.
>   Replace the currently playable item by calling`codeph  MediaPlayer.replaceCurrentResource()` and passing an existing `codeph  MediaResource` instance.
>   This starts the resource loading process.
>   
>   
>   
>1. Register the `codeph  MediaPlayerEvent.STATUS_CHANGED` event with the `codeph  MediaPlayer` instance. In the callback, check for at least the following status values:
>    * `codeph  MediaPlayerStatus.PREPARED`
>    * `codeph  MediaPlayerStatus.INITIALIZED`
>    * `codeph  MediaPlayerStatus.ERROR`
>   Through these events, the`codeph  MediaPlayer` object notifies your application when it has successfully loaded the media resource.
>   
>1. When the status of the media player changes to `codeph  INITIALIZED`, you can call `codeph  MediaPlayer.prepareToPlay()`.
>   This status indicates that the media has been successfully loaded. The new`codeph  MediaPlayerItem` is ready for playback. Calling `codeph  prepareToPlay()` starts the advertising resolution and placement process, if any.
>   
>   
