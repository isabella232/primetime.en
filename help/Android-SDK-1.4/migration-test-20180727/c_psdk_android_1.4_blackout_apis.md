---
description: provides API elements that are useful when implementing blackouts, including methods, metadata, and notifications.
seo-description: provides API elements that are useful when implementing blackouts, including methods, metadata, and notifications.
seo-title: Blackout API elements
title: Blackout API elements
uuid: 26c2e240-9216-468f-b7da-4d3f66a85796
index: n
internal: n
snippet: y
translate: y
---

# Blackout API elements

You can use the following when implementing a blackout solution in your player. 
* **MediaPlayer** 
    * `registerCurrentItemAsBackgroundItem` Saves the currently loaded resource as the background resource. If `replaceCurrentResource` is called after this method,  <!-- PH element: phrases/primetime-sdk-name --> continues to download the background item’s manifest until you call `unregisterCurrentBackgroundItem`, `release`, or `reset`. 

    * `unregisterCurrentBackgroundItem` Sets the background item to null and stops fetching and parsing the background manifest.


* **BlackoutMetadata** - A Metadata class that is specific to blackouts.
  This allows you to set nonseekable ranges (an array of `TimeRanges`) on  <!-- PH element: phrases/primetime-sdk-name --> . <!-- PH element: phrases/primetime-sdk-name --> checks for these ranges every time the user seeks. If it is set and the user seeks into a nonseekable range, <!-- PH element: phrases/primetime-sdk-name --> forces the viewer to the end of the nonseekable range.

* **START HERE NEXT****AdvertisingMetadata** Enable or disable preroll on a live stream by setting `enableLivePreroll` to true or false. If false,  <!-- PH element: phrases/primetime-sdk-name --> does not make an explicit ad server call for pre-roll ads before the content playback and so does not play the pre-roll. This has no impact on the mid-rolls. The default is true.

* **MediaPlayer.BlackoutsEventListener** 
    * `onTimedMetadataInBackgroundItem` - Dispatched when detects a subscribed tag in the background manifest and a new `TimedMetadata` instance is prepared from it. The `TimedMetadata` instance is dispatched as a parameter.
    * `onBackgroundManifestFailed` - Dispatched when the media player completely fails to load the background manifest, that is, all of the stream URLs return either an error or an invalid response.

* **Notifications** 
    * `BACKGROUND_MANIFEST_WARNING`     
        * Code: 204000
        * Type: Warning
        * Error in background manifest download.



