---
description: The MediaPlayer interface for Android encapsulates the functionality and behavior of a media player.
seo-description: The MediaPlayer interface for Android encapsulates the functionality and behavior of a media player.
seo-title: Set up the MediaPlayer
title: Set up the MediaPlayer
---

# Set up the MediaPlayer

provides one implementation of the `codeph  MediaPlayer` interface, the `codeph  DefaultMediaPlayer` class. When you need video playback functionality, instantiate `codeph  DefaultMediaPlayer`.

>[!TIP]
>
>Interact with the`codeph  DefaultMediaPlayer` instance only with the methods that are exposed by the `codeph  MediaPlayer` interface.
>1. Instantiate a MediaPlayer using the public `codeph  DefaultMediaPlayer.create` factory method, passing a Java Android application context object.
>   ```java
>   public static MediaPlayer create(Context context) 
>   
>   ```
>   
>   
>1. Call `codeph  MediaPlayer.getView` to get a reference to the `codeph  MediaPlayerView` instance.
>   ```java
>   MediaPlayerView getView() throws IllegalStateException; 
>   
>   ```
>   
>   
>1. Place the `codeph  MediaPlayerView` instance in a `codeph  FrameLayout` instance, which places the video on the device's screen.
>   ```java
>   FrameLayout playerFrame = (FrameLayout) view.findViewById(R.id.playerFrame); 
>   playerFrame.addView(mediaPlayer.getView()); 
>   
>   ```
>   
>   
>   
