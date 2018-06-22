---
description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-title: Load a media resource in the MediaPlayer
title: Load a media resource in the MediaPlayer
---

# Load a media resource in the MediaPlayer

>1. Set your MediaPlayer's playable item with the new resource to be played.
>   Replace your existing MediaPlayer's currently playable item by calling `codeph  MediaPlayer.replaceCurrentItem` and passing an existing `codeph  MediaResource` instance.
>   
>   
>   
>1. Register an implementation of the `codeph  MediaPlayer.PlaybackEventListener` interface with the `codeph  MediaPlayer` instance.
>* `codeph  onPrepared`
>* `codeph  onStateChanged`, and check for INITIALIZED and ERROR.
>   
>   
>1. When the state of the media player changes to INITIALIZED, you can call `codeph  MediaPlayer.prepareToPlay`
>   The INITIALIZED state indicates that the media has been successfully loaded. Calling`codeph  prepareToPlay` starts the advertising resolution and placement process, if any.
>   
>1. When  calls the `codeph  onPrepared` callback, the media stream has successfully loaded and is prepared for playback.
>   When the media stream is loaded, a`codeph  MediaPlayerItem` is created.
>   
>   
