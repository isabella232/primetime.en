---
description: You can display the duration of the currently active content.
seo-description: You can display the duration of the currently active content.
seo-title: Display the duration of the video
title: Display the duration of the video
uuid: 945f222d-80ba-4832-a06f-9bb8db6adbcb
---

# Display the duration of the video {#display-the-duration-of-the-video}

You can display the duration of the currently active content.

  Implement a video-duration display using the following sample code:

       The `PTMediaPlayer` property, ` [seekableRange](https://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTMediaPlayer.html#//api/name/seekableRange)`, contains the current seekable window range:

    * For VOD, this range is the entire VOD content range, including ads. 
    * For live/linear, this range represents the seekable window.

       For more information about the API, see [TVSDK 3.4 for iOS API Reference](https://help.adobe.com/en_US/primetime/api/psdk/appledoc_v3/index.html)

<!--<a id="example_A153BE3AC03F43C6BF3A156316A08CD3"></a>-->

```
CMTimeRange seekableRange = self.player.seekableRange;  
if (CMTIMERANGE_IS_VALID(seekableRange)) { 
    double start = CMTimeGetSeconds(seekableRange.start);  
    double duration = CMTimeGetSeconds(seekableRange.duration); 
}
```