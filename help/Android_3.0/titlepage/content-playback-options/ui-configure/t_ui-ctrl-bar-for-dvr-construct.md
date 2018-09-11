---
description: You can implement a control bar with DVR support for VOD and live streaming. DVR support includes the concept of a seekable window and the client live point.
seo-description: You can implement a control bar with DVR support for VOD and live streaming. DVR support includes the concept of a seekable window and the client live point.
seo-title: Construct a control bar enhanced for DVR
title: Construct a control bar enhanced for DVR
uuid: 3e447c7c-9757-4f94-a4d9-46d59b7a348e
index: y
internal: n
snippet: y
translate: y
---

# Construct a control bar enhanced for DVR

You can implement a control bar with DVR support for VOD and live streaming. DVR support includes the concept of a seekable window and the client live point.


* For VOD, the length of the seekable window is the duration of the entire asset.
* For live streaming, the length of the DVR (seekable) window is defined as the time range that starts at the live playback window and ends at the client live point. Remember the following information: 
    * The client live point is calculated by subtracting the buffered length from the live window end. The target duration is a value bigger than or equal to the maximum duration of a fragment in the manifest. 
    
    * The default value is 10000 ms.    
    * The control bar for live playback supports DVR by first positioning the thumb at the client live point when starting playback and by displaying a region that marks the area where seek is not allowed.    
    
    




<a id="fig_37A39A28BA714BA5A2C461357ED5BD41"></a> ![](assets/dvr-window.PNG) 

1. To implement a control bar with DVR support, follow the steps in [Display a seek scrub bar with the current playback position...](../../../titlepage/content-playback-options/ui-configure/t_ui-seek-scrub-bar-display.md#display-seek-scrub-bar) with the following differences:

    
    * You can implement a control bar that is mapped only for the seekable range instead of for the playback range. Any user interaction for seek can be considered safe in the seekable range. 
    
    * You can implement a control bar that is mapped for the playback range but that also displays the seekable range.    
    
    

    
       For a control bar:     
    1. Add an overlay to the control bar that represents the playback range.1. When the user starts to seek, check whether the desired seek position is within the seekable range using `MediaPlayer.getSeekableRange`.    
    
    

    
       For example:     
       ```
       java       TimeRange seekableRange = _mediaPlayer.getSeekableRange(); 
       if (seekableRange.contains(desiredSeekPosition)) { 
           _mediaPlayer.seek(desiredPosition); 
       }
       ```

    
       You can also choose to seek to the client live point using the `MediaPlayer.LIVE_POINT` constant.     
       ```
       mediaPlayer.seek(MediaPlayer.LIVE_POINT);
       ```

    
