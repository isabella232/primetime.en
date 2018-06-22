---
description: provides API elements that are useful when implementing blackouts, including methods, metadata, and notifications.
seo-description: provides API elements that are useful when implementing blackouts, including methods, metadata, and notifications.
seo-title: Blackout API elements
title: Blackout API elements
---

# Blackout API elements

You can use the following when implementing a blackout solution in your player.
* **MediaPlayer**
    * `codeph registerCurrentItemAsBackgroundItem`
      Saves the currently loaded resource as the background resource. If `codeph replaceCurrentResource` is called after this method,  continues to download the background item’s manifest until you call `codeph unregisterCurrentBackgroundItem`, `codeph release`, or `codeph reset`.
      
      
    * `codeph unregisterCurrentBackgroundItem`
      Sets the background item to null and stops fetching and parsing the background manifest.
      
      
  
* **BlackoutMetadata** -
  A Metadata class that is specific to blackouts.
  
  This allows you to set nonseekable ranges (an array of `codeph TimeRanges`) on .  checks for these ranges every time the user seeks. If it is set and the user seeks into a nonseekable range,  forces the viewer to the end of the nonseekable range.
  
  
* **START HERE NEXT****AdvertisingMetadata**
  Enable or disable preroll on a live stream by setting `codeph enableLivePreroll` to true or false. If false,  does not make an explicit ad server call for pre-roll ads before the content playback and so does not play the pre-roll. This has no impact on the mid-rolls. The default is true.
  
  
* **MediaPlayer.BlackoutsEventListener**
    * `codeph onTimedMetadataInBackgroundItem` - Dispatched when detects a subscribed tag in the background manifest and a new `codeph TimedMetadata` instance is prepared from it. The `codeph TimedMetadata` instance is dispatched as a parameter.
    * `codeph onBackgroundManifestFailed` - Dispatched when the media player completely fails to load the background manifest, that is, all of the stream URLs return either an error or an invalid response.
  
* **Notifications**
    * `codeph BACKGROUND_MANIFEST_WARNING`
        * Code: 204000
        * Type: Warning
        * Error in background manifest download.
      
  

