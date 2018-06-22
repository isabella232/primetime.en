---
description: The MediaPlayer interface encapsulates the functionality and behavior of a media player. WRITER: The Android/DHLS procedures are very similar, but diff enough to be easier to put into separate files for now.
seo-description: The MediaPlayer interface encapsulates the functionality and behavior of a media player. WRITER: The Android/DHLS procedures are very similar, but diff enough to be easier to put into separate files for now.
seo-title: Set up the MediaPlayer
title: Set up the MediaPlayer
---

# Set up the MediaPlayer

provides a single implementation of the `codeph  MediaPlayer` interface: the DefaultMediaPlayer class. When you need video-playback functionality, instantiate `codeph  DefaultMediaPlayer`.

>[!NOTE]
>
>Interact with the`codeph  DefaultMediaPlayer` instance only with the methods exposed by the `codeph  MediaPlayer` interface.
>1. Instantiate a `codeph  MediaPlayerContext` using the application-loaded `codeph  authorizedFeatures` instance (see []()).
>   ```
>   var context:MediaPlayerContext = 
>    new MediaPlayerContext(authorizedFeatures)
>   ```
>   
>   
>1. Instantiate a `codeph  MediaPlayer` using the public create factory method, passing a `codeph  MediaPlayerContext` context object:
>   ```
>   public static function create(context:Context):MediaPlayer
>   ```
>   
>       
>       `codeph  MediaPlayer`
>   
>1. Instantiate a `codeph  MediaPlayerView` and specify the StageVideo instance to be used:
>   ```
>   var view:MediaPlayerView = 
>    MediaPlayerView.create(stage.stageVideos[0] )
>   ```
>   
>   
>1. Associate the `codeph  MediaPlayerView` instance with the newly created view:
>   ```
>   mediaPlayer.view = view;
>   ```
>   <!-- Q: Oh? Suddenly there's a lowercase mediaPlayer; where did that come from? -elf June 28 '16 -->
>   
>1. Place the `codeph  MediaPlayerView` instance on the device's screen:
>   ```
>   container.addChild(view)
>   ```
>   
>   
>   
