---
description: You can add pause and play buttons to pause or play your video.
seo-description: You can add pause and play buttons to pause or play your video.
seo-title: Play and pause a video
title: Play and pause a video
uuid: 9501fc79-721e-407d-9847-ac0191f31d4c
index: n
internal: n
snippet: y
translate: y
---

# Play and pause a video


>1. To create a pause or play button:
>   >1. Wait for the player to be in at least the prepared state.
>   >1. To start playback, call the ` play` method:
>   >
>   >   ```
>   >   java>   >   void play() throws MediaPlayerException;
>   >   ```
>   >
>   >1. To pause playback, call the ` pause()` method:
>   >
>   >   ```
>   >   java>   >   void pause() throws MediaPlayerException;
>   >   ```
>   >
>1. Use the status changed event callback to check for errors or to take other appropriate actions.
>   <!-- PH element: phrases/primetime-sdk-name --> calls this callback for ` pause()` or ` play()` and passes information about the status change, including the new status, such as paused or playing. 
>
