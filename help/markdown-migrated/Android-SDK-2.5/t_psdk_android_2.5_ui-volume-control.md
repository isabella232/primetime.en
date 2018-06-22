---
description: You can set up a user interface control to adjust the volume for the video.
seo-description: You can set up a user interface control to adjust the volume for the video.
seo-title: Provide volume control
title: Provide volume control
---

# Provide volume control

>1. In the callback routine for the volume control interface element, ensure that the player is in a valid status for this command.
>   >[!TIP]
>   >
>   >Any status, except for RELEASED is valid.
>   
>   
>1. Call `codeph  setVolume` to set the audio volume.
>   For example:
>   ```java
>   void setVolume(int volume) throws MediaPlayerException;
>   ```
>   
>   The value for the volume represents the requested volume expressed as a proportion of the maximum volume, where `codeph  0` is silent and `codeph  1` is the maximum volume.
>   
>   
>   
>   
