---
description: To display banner ads, you need to create banner instances and allow to listen for ad-related events.
seo-description: To display banner ads, you need to create banner instances and allow to listen for ad-related events.
seo-title: Display banner ads
title: Display banner ads
uuid: f67f8661-a0b2-4fbd-966b-07f98abfe974
index: n
internal: n
snippet: y
translate: y
---

# Display banner ads

 <!-- PH element: phrases/primetime-sdk-name --> provides a list of companion banner ads that are associated with a linear ad through the `AdPlaybackEventListener.onAdBreakStart` event. 
Manifests can specify companion banner ads by: 
* An HTML snippet
* The URL of an iFrame page
* The URL of a static image or an Adobe Flash SWF file

For each companion ad,  <!-- PH element: phrases/primetime-sdk-name --> indicates which types are available for your application.

>1. Add a listener for the `AdPlaybackEventListener.onAdBreakStart` event that does the following:
>    
>    * Clears existing ads in the banner instance.
>    * Gets the list of companion ads from `Ad.getCompanionAssets`.
>    * If the list of companion ads is not empty, iterate over the list for banner instances. Each banner instance (an `AdAsset`) contains information, such as width, height, resource type (html, iframe, or static), and data that is required to display the companion banner. 

>    * If a video ad has no companion ads booked with it, the list of companion assets contains no data for that video ad.
>    * To show a standalone display ad, add the logic to your script to run a normal DFP (DoubleClick for Publishers) display ad tag in the appropriate banner instance.
>    * Sends the banner information to a function on your page that displays the banners in an appropriate location. This is usually a `div`, and your function uses the `div ID` to display the banner. 

>    
