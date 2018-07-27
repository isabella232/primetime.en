---
description: By using custom ad markers, you can mark specific sections of the main content as ad-related content periods.
seo-description: By using custom ad markers, you can mark specific sections of the main content as ad-related content periods.
seo-title: Add custom ad markers
title: Add custom ad markers
uuid: ee0d24ad-2e70-4f08-a5d6-185245e5facd
index: n
internal: n
snippet: y
translate: y
---

# Add custom ad markers

This feature is most useful when content is being recorded, for example, from a live event, and the result of the recording is one HLS stream. The recording contains main content and advertising-related content in one HLS video-on-demand (VOD) stream. The recording process does not keep track of the ad-related segments, so the information that is related to the positioning of the ads in the main content is lost.
You might be able to obtain the information that is related to the positioning of the ad-content periods from other out-of-band sources, such as external CMS systems. You can define custom markers, through which this out-of-band information can be passed to the timeline manager subsystem. The intention is to mark the content sections that match the specified ad-related content in such a way that all ad-specific playback events are triggered in the same manner as if these custom ad-periods were explicitly placed on the player's timeline.
Ad tracking is not handled internally by  <!-- PH element: phrases/primetime-sdk-name --> , such as when ads are resolved by <!-- PH element: phrases/auditude-name-long --> (previously known as <!-- PH element: phrases/auditude-name-previously-known-as --> ). However, <!-- PH element: phrases/primetime-sdk-name --> provides the following abstractions that define the way ad-related content is represented on the timeline:
* The ad break An ad break is an ordered list of individual consecutive ads.

* An individual ad

Playback events are triggered separately for ad breaks and ads at the starting and ending point for each ad.
<!-- PH element: phrases/primetime-sdk-name --> dispatches ad tracking events to your application, so you can implement your own tracking logic. If you set custom ad markers, you receive the `onAdBreakStart`, `onAdStart`, `onAdProgress`, `onAdComplete`, and `onAdBreakComplete` events. 
