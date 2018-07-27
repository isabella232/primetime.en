---
description: You can set up a user interface control for sound volume.
seo-description: You can set up a user interface control for sound volume.
seo-title: Provide volume control
title: Provide volume control
uuid: d9daf25f-396d-45de-8f4a-beab514c66bb
index: n
internal: n
snippet: y
translate: y
---

# Provide volume control


>1. Wait for the MediaPlayer instance to be in a valid state for this command, which is any except RELEASED or ERROR.
>1. Call ` setVolume` on the ` MediaPlayer` instance to set the audio volume.
>
>   ```
>   java>   void setVolume(int volume) throws IllegalStateException;
>   ```
>   The value for the volume represents the requested volume expressed as a proportion of the maximum volume, where 0 is silent and 100 is the maximum volume.
>
