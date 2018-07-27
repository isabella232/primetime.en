---
description: You can add behavior to pause and play buttons.
seo-description: You can add behavior to pause and play buttons.
seo-title: Play and pause a video
title: Play and pause a video
uuid: c6e1f827-0b6f-40db-a7c6-75287177bc33
index: n
internal: n
snippet: y
translate: y
---

# Play and pause a video


>1. Create a pause/play button that does the following.
>   >1. Wait for your player to be in at least the PREPARED state.
>   >1. To start playback, call the  <!-- PH element: phrases/primetime-sdk-name --> play method:
>   >
>   >   ```
>   >   java>   >   void play() throws IllegalStateException;
>   >   ```
>   >
>   >1. To pause playback, call the  <!-- PH element: phrases/primetime-sdk-name --> pause method:
>   >
>   >   ```
>   >   java>   >   void pause() throws IllegalStateException;
>   >   ```
>   >
>1. Use the ` MediaPlayer.PlaybackEventListener.onStateChanged` callback to check for errors or to take other appropriate actions.
>   <!-- PH element: phrases/primetime-sdk-name --> calls this callback when the pause or play method is called. <!-- PH element: phrases/primetime-sdk-name --> passes information about the state change in the callback, including the new state, such as PAUSED or PLAYING.
>
