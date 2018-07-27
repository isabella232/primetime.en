---
description: provides API elements that are useful when implementing blackouts, including methods, metadata, and notifications.
seo-description: provides API elements that are useful when implementing blackouts, including methods, metadata, and notifications.
seo-title: Blackout API elements
title: Blackout API elements
uuid: d7c766b0-2729-4e21-98df-7a70942eb7b5
index: n
internal: n
snippet: y
translate: y
---

# Blackout API elements

You can use the following when implementing a blackout solution in your player. 
* **MediaPlayer** 
    * `registerCurrentItemAsBackgroundItem` Saves the currently loaded resource as the background resource. If `replaceCurrentResource` is called after this method,  <!-- PH element: phrases/primetime-sdk-name --> continues to download the background item’s manifest until you call `unregisterCurrentBackgroundItem`. 

    * `unregisterCurrentBackgroundItem` Clears the currently set background resource and stops fetching and parsing the background manifest.


* **BlackoutMetadata** A Metadata type that is specific to blackouts.
  This allows you to set nonseekable ranges (an additional `TimeRange` attribute called `nonseekableRange`) on  <!-- PH element: phrases/primetime-sdk-name --> . <!-- PH element: phrases/primetime-sdk-name --> checks for these ranges (whether the desired seek position falls within a `nonseekableRange`) every time the user seeks. If it is set and the user seeks into a nonseekable range,  <!-- PH element: phrases/primetime-sdk-name --> forces the viewer to the end time of the `seekableRange`. 

* **START HERE NEXT** **DefaultMetadataKeys** Enable or disable preroll on a live stream by setting `ENABLE_LIVE_PREROLL` to true or false. If false,  <!-- PH element: phrases/primetime-sdk-name --> does not make an explicit ad server call for pre-roll ads before the content playback and so does not play the pre-roll. This has no impact on the mid-rolls. The default is true.

* **TimedMetadataEvent** 
    * `TIMED_METADATA_IN_BACKGROUND_AVAILABLE` event subtype - Dispatched when  <!-- PH element: phrases/primetime-sdk-name --> detects a subscribed tag in the background manifest.

* **Notifications** 
    * `BACKGROUND_MANIFEST_WARNING`     
        * Code: 204000
        * Type: Warning
        * Error in background manifest download.

    * `SeekEvent.SEEK_POSITION_ADJUSTED` Dispatched when a seek is attempted in a nonseekable range.



