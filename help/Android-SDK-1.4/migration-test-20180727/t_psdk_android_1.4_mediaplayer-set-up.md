---
description: The MediaPlayer interface for Android encapsulates the functionality and behavior of a media player.
seo-description: The MediaPlayer interface for Android encapsulates the functionality and behavior of a media player.
seo-title: Set up the MediaPlayer
title: Set up the MediaPlayer
uuid: 7f329f73-18b8-4d6b-91c3-c2f3af7554de
index: n
internal: n
snippet: y
translate: y
---

# Set up the MediaPlayer

 <!-- PH element: phrases/primetime-sdk-name --> provides one implementation of the ` MediaPlayer` interface, the ` DefaultMediaPlayer` class. When you need video playback functionality, instantiate ` DefaultMediaPlayer`. 

>[!TIP]
>
>Interact with the ` DefaultMediaPlayer` instance only with the methods that are exposed by the ` MediaPlayer` interface. 


>1. Instantiate a MediaPlayer using the public ` DefaultMediaPlayer.create` factory method, passing a Java Android application context object.
>
>   ```
>   java>   public static MediaPlayer create(Context context) 
>   
>   ```
>
>1. Call ` MediaPlayer.getView` to get a reference to the ` MediaPlayerView` instance.
>
>   ```
>   java>   MediaPlayerView getView() throws IllegalStateException; 
>   
>   ```
>
>1. Place the ` MediaPlayerView` instance in a ` FrameLayout` instance, which places the video on the device's screen.
>
>   ```
>   java>   FrameLayout playerFrame = (FrameLayout) view.findViewById(R.id.playerFrame); 
>   playerFrame.addView(mediaPlayer.getView()); 
>   
>   ```
>
