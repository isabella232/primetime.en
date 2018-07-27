---
description: You can control the position and size of the video view using the MediaPlayerView object.
seo-description: You can control the position and size of the video view using the MediaPlayerView object.
seo-title: Control the position and size of the video view
title: Control the position and size of the video view
uuid: a9b71c88-c1c0-4d49-9afc-bbc821d6303b
index: n
internal: n
snippet: y
translate: y
---

# Control the position and size of the video view

 <!-- PH element: phrases/primetime-sdk-name --> by default attempts to maintain the aspect ratio of the video view whenever the size or the position of the video changes (due to a change made by the application, or by a profile switch, or a content switch, etc.).
You can override the default aspect ratio behavior by specifying a different *scale policy*. Specify the scale policy using the ` MediaPlayerView` object's ` scalePolicy` property. The ` MediaPlayerView`'s default scale policy is set with an instance of the ` MaintainAspectRatioScalePolicy` class. To reset the scale policy, replace the default instance of ` MaintainAspectRatioScalePolicy` on ` MediaPlayerView.scalePolicy` with your own policy. (You cannot set the ` scalePolicy` property to a null value.) 

>1. Implement the ` MediaPlayerViewScalePolicy` interface to create your own scale policy.
>   The ` MediaPlayerViewScalePolicy` has one method: >
>   ```
>   public function adjust(viewPort:Rectangle, 
>     videoWidth:Number, videoHeight:Number):Rectangle;
>   ```

>   >[!NOTE]
>   >
>   ><!-- PH element: phrases/primetime-sdk-name --> uses a ` StageVideo` object for displaying the video, and because ` StageVideo` objects are not on the display list, the ` viewPort` parameter contains the absolute coordinates of the video. For example: >   >
>   >```
>   >public class CustomScalePolicy implements MediaPlayerViewScalePolicy { 
>   >    /** 
>   >     * Default constructor. 
>   >     */ 
>   >    public function CustomScalePolicy() { 
>   >    } 
>   > 
>   >    public function adjust(viewPort:Rectangle,  
>   >                           videoWidth:Number,  
>   >                           videoHeight:Number):Rectangle { 
>   >        return customAdjustment(); 
>   >    } 
>   > 
>   >    public function customAdjustment():Rectangle { 
>   >        /* Your custom adjustment here */ 
>   >        [...] 
>   >    } 
>   >}
>   >```


>
>1. Assign your implementation to the ` MediaPlayerView` property.
>
>   ```
>   var view:MediaPlayerView = MediaPlayerView.create(stage.stageVideos[0]); 
>   view.scalePolicy = new CustomScalePolicy();
>   ```
>
>1. Add your view to the Media Player's ` view` property.
>
>   ```
>   addChild(view); 
>    
>   mediaPlayer.view = view;
>   ```
>
