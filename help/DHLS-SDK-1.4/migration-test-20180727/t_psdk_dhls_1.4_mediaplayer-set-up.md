---
description: The MediaPlayer interface encapsulates the functionality and behavior of a media player. WRITER: The Android/DHLS procedures are very similar, but diff enough to be easier to put into separate files for now.
seo-description: The MediaPlayer interface encapsulates the functionality and behavior of a media player. WRITER: The Android/DHLS procedures are very similar, but diff enough to be easier to put into separate files for now.
seo-title: Set up the MediaPlayer
title: Set up the MediaPlayer
uuid: 11cb640f-b6ae-438b-8c80-007868698fb8
index: n
internal: n
snippet: y
translate: y
---

# Set up the MediaPlayer

 <!-- PH element: phrases/primetime-sdk-name --> provides a single implementation of the ` MediaPlayer` interface: the DefaultMediaPlayer class. When you need video-playback functionality, instantiate ` DefaultMediaPlayer`. 

>[!NOTE]
>
>Interact with the ` DefaultMediaPlayer` instance only with the methods exposed by the ` MediaPlayer` interface. 


>1. Instantiate a ` MediaPlayerContext` using the application-loaded ` authorizedFeatures` instance (see  get-signed-token ).
>
>   ```
>   var context:MediaPlayerContext =  
>       new MediaPlayerContext(authorizedFeatures)
>   ```
>
>1. Instantiate a ` MediaPlayer` using the public create factory method, passing a ` MediaPlayerContext` context object:
>
>   ```
>   public static function create(context:Context):MediaPlayer
>   ```
>

>       ` MediaPlayer`1. Instantiate a ` MediaPlayerView` and specify the StageVideo instance to be used:
>
>   ```
>   var view:MediaPlayerView =  
>       MediaPlayerView.create(stage.stageVideos[0] )
>   ```
>
>1. Associate the ` MediaPlayerView` instance with the newly created view:
>
>   ```
>   mediaPlayer.view = view;
>   ```
>   <!-- Q: Oh? Suddenly there's a lowercase mediaPlayer; where did that come from? -elf June 28 '16 -->>
>1. Place the ` MediaPlayerView` instance on the device's screen:
>
>   ```
>   container.addChild(view)
>   ```
>
