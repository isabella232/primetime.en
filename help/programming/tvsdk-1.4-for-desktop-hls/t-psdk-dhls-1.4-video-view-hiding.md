---
description: After a MediaPlayer view has been used to play video, you can hide it and display it again by using a TVSDK method or manually.
seo-description: After a MediaPlayer view has been used to play video, you can hide it and display it again by using a TVSDK method or manually.
seo-title: Hide a video view
title: Hide a video view
uuid: 7cc02bf4-41ee-4af0-98ba-df070b50b88d
---

# Hide a video view{#hide-a-video-view}

After a MediaPlayer view has been used to play video, you can hide it and display it again by using a TVSDK method or manually.

 You must pause a video before clearing it or moving it from the display. 
* Option 1: Clear the video frame with `MediaPlayer.clearVideo`​ and replace the frame later.
  * Pause the video that you want to hide.
  * Remove the displayed video frame by calling `MediaPlayer.clearVideo`.
  * To reset the `MediaPlayer` so that it can be played again, call `replaceCurrentResource` or `replaceCurrentItem`.
* Option 2: Move the `MediaPlayer` view off the screen and move it back later without having to replace it.
  * Pause the video that you want to hide.
  * Move the view out of the stage. For example:

    ```  
    view.x = -300; 
    view.y = -300;
    ```  
  
  * To display the video again, move the view back into the stage.
