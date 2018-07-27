---
description: When a user clicks on an ad or a related button, your application must respond. provides you with information about the destination URL for the click.
seo-description: When a user clicks on an ad or a related button, your application must respond. provides you with information about the destination URL for the click.
seo-title: Respond to clicks on ads
title: Respond to clicks on ads
uuid: 11ceda82-02c2-46c1-aba3-8bbe7166c2a1
index: n
internal: n
snippet: y
translate: y
---

# Respond to clicks on ads


>1. To set up an event listener for  <!-- PH element: phrases/primetime-sdk-name --> , and provide the click-through information, register ` AdClickedEventListener.onAdClicked`.
>   When a user clicks on an ad or a related button, <!-- PH element: phrases/primetime-sdk-name --> dispatches this notification, including information about the destination for the click.>
>1. Monitor user interactions on clickable ads.
>1. When the user touches or clicks the ad or button, to notify  <!-- PH element: phrases/primetime-sdk-name --> , call ` notifyClick` on the ` MediaPlayerView`.
>1. Listen for the ` onAdClick(AdClickEvent event)` event from  <!-- PH element: phrases/primetime-sdk-name --> .
>1. To retrieve the click-through URL and related information, use the getter methods for the ` AdClickEvent` instance.
>1. Pause the video.
>   For more information about pausing the video, see pausing-resuming-playback .>
>1. Use the click-through information to display the ad click-through URL and the related information.
>       You can, for example, display the information in one of the following ways:>    
>    * In your application, by opening the click-through URL in a browser. On desktop platforms, the video ad playback area is used to invoke click-through URLs at user clicks.

>    * Redirect users to their external mobile web browser. On mobile devices, the video ad playback area is used for other functions, such as hiding and showing controls, pausing playback, expanding to full screen, and so on. On these devices, a separate view such as a sponsor button, is used to launch the click-through URL.

>    
>1. Close the browser window in which the click-through information is displayed and resume playing the video.
