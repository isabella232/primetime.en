---
description: You can set up a user interface control for sound volume.
seo-description: You can set up a user interface control for sound volume.
seo-title: Provide volume control
title: Provide volume control
uuid: 5f2f69cc-3969-4ca2-8ab9-5713fdf5cdb8
---

# Provide volume control{#provide-volume-control}

You can set up a user interface control for sound volume.

1. Wait for the `MediaPlayer` instance to be in a valid state for this command.

   Any state except for RELEASED or ERROR is valid.
1. Set the volume attribute on the `MediaPlayer` instance to set the audio volume.

   ```js
   player.volume = ...
   ```

   The value for the volume represents the requested volume expressed as a proportion of the maximum volume, where 0 is silent and is the maximum volume.

