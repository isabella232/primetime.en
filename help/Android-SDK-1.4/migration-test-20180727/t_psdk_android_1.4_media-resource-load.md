---
description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-title: Load a media resource in the MediaPlayer
title: Load a media resource in the MediaPlayer
uuid: c8dae2e9-44a4-49f2-8fe6-09e3a49c820f
index: n
internal: n
snippet: y
translate: y
---

# Load a media resource in the MediaPlayer


>1. Set your MediaPlayer's playable item with the new resource to be played.
>   Replace your existing MediaPlayer's currently playable item by calling ` MediaPlayer.replaceCurrentItem` and passing an existing ` MediaResource` instance. 
>
>1. Register an implementation of the ` MediaPlayer.PlaybackEventListener` interface with the ` MediaPlayer` instance.
>    
>    * ` onPrepared`
>    * ` onStateChanged`, and check for INITIALIZED and ERROR.
>    
>1. When the state of the media player changes to INITIALIZED, you can call ` MediaPlayer.prepareToPlay`
>   The INITIALIZED state indicates that the media has been successfully loaded. Calling ` prepareToPlay` starts the advertising resolution and placement process, if any.>
>1. When  <!-- PH element: phrases/primetime-sdk-name --> calls the ` onPrepared` callback, the media stream has successfully loaded and is prepared for playback.
>   When the media stream is loaded, a ` MediaPlayerItem` is created.>
