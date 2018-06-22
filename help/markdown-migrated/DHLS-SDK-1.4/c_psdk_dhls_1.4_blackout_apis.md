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
      Saves the currently loaded resource as the background resource. If `codeph replaceCurrentResource` is called after this method,  continues to download the background item’s manifest until you call `codeph unregisterCurrentBackgroundItem`.
      
      
    * `codeph unregisterCurrentBackgroundItem`
      Clears the currently set background resource and stops fetching and parsing the background manifest.
      
      
  
* **BlackoutMetadata**
  A Metadata type that is specific to blackouts.
  
  This allows you to set nonseekable ranges (an additional `codeph TimeRange` attribute called `codeph nonseekableRange`) on .  checks for these ranges (whether the desired seek position falls within a `codeph nonseekableRange`) every time the user seeks. If it is set and the user seeks into a nonseekable range,  forces the viewer to the end time of the `codeph seekableRange`.
  
  
* **START HERE NEXT** **DefaultMetadataKeys**
  Enable or disable preroll on a live stream by setting `codeph ENABLE_LIVE_PREROLL` to true or false. If false,  does not make an explicit ad server call for pre-roll ads before the content playback and so does not play the pre-roll. This has no impact on the mid-rolls. The default is true.
  
  
* **TimedMetadataEvent**
    * `codeph TIMED_METADATA_IN_BACKGROUND_AVAILABLE` event subtype - Dispatched when  detects a subscribed tag in the background manifest.
  
* **Notifications**
    * `codeph BACKGROUND_MANIFEST_WARNING`
        * Code: 204000
        * Type: Warning
        * Error in background manifest download.
      
    * `codeph SeekEvent.SEEK_POSITION_ADJUSTED`
      Dispatched when a seek is attempted in a nonseekable range.
      
      
  

