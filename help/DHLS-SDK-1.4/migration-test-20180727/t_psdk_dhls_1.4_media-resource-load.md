---
description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-description: Load a resource by directly instantiating a MediaResource and loading the video content to be played. This is one way of loading a media resource.
seo-title: Load a media resource in the MediaPlayer
title: Load a media resource in the MediaPlayer
uuid: 57de6e27-9cd3-4b50-a99f-e9eb8dd28c03
index: n
internal: n
snippet: y
translate: y
---

# Load a media resource in the MediaPlayer


>1. Set your ` MediaPlayer` object's playable item with the new resource to be played.
>   Replace your existing MediaPlayer's currently playable item by calling ` MediaPlayer.replaceCurrentResource` and passing an existing ` MediaResource` instance. 
>
>1. Check for at least the following changes:
>    
>    * INITIALIZED
>    * PREPARED
>    * ERROR
>       Through these events, the ` MediaPlayer` object can notify your application when the media resource is successfully loaded. 
>    
>1. When the state of the media player changes to INITIALIZED, you can call ` MediaPlayer.prepareToPlay`
>   The INITIALIZED state indicates that the media has been successfully loaded. Calling ` prepareToPlay` starts the advertising resolution and placement process, if any.>
>1. When the media player status changes to PREPARED, the media stream has successfully loaded and is prepared for playback.
>   When the media stream is loaded, a ` MediaPlayerItem` is created.>
