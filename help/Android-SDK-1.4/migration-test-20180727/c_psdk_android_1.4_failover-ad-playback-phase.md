---
description: downloads the ad segments and renders them on the device's screen.
seo-description: downloads the ad segments and renders them on the device's screen.
seo-title: Ad-playback phase
title: Ad-playback phase
uuid: 009baeee-9ae8-4336-9537-e08004daa87d
index: n
internal: n
snippet: y
translate: y
---

# Ad-playback phase

At this point,  <!-- PH element: phrases/primetime-sdk-name --> has resolved ads, positioned them on the timeline, and attempts to render the content on the screen.
The following main classes of errors might occur in this phase: 
* Errors when connecting to the host server
* Errors when downloading the manifest file
* Errors when downloading the media segments

For all three error classes,  <!-- PH element: phrases/primetime-sdk-name --> forwards triggered events to your application, including:
* Notification events triggered when a failover happens.
* Notification events when the profile is changed because of the failover algorithm.
* Notification events triggered when all failover options have been considered, and no additional action can be taken automatically. Your application needs to take the appropriate action.


Whether or not errors occur,  <!-- PH element: phrases/primetime-sdk-name --> calls onAdBreakComplete for each `onAdBreakStart` and `onAdComplete` for every `onAdStart`. However, if segments could not be downloaded, there might be gaps in the timeline. When the gaps are large enough, the values in the playhead position and the reported ad progress might exhibit discontinuities. 
