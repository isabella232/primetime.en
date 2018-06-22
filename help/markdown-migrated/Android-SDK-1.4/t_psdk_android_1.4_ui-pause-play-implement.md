---
description: You can add behavior to pause and play buttons.
seo-description: You can add behavior to pause and play buttons.
seo-title: Play and pause a video
title: Play and pause a video
---

# Play and pause a video

>1. Create a pause/play button that does the following.
>   >1. Wait for your player to be in at least the PREPARED state.
>   >   
>   >1. To start playback, call the  play method:
>   >   ```java
>   >   void play() throws IllegalStateException;
>   >   ```
>   >   
>   >   
>   >1. To pause playback, call the  pause method:
>   >   ```java
>   >   void pause() throws IllegalStateException;
>   >   ```
>   >   
>   >   
>   >   
>   
>1. Use the `codeph  MediaPlayer.PlaybackEventListener.onStateChanged` callback to check for errors or to take other appropriate actions.
>   calls this callback when the pause or play method is called.  passes information about the state change in the callback, including the new state, such as PAUSED or PLAYING.
>   
>   
>   
>   
