---
description: provides API elements that are useful when implementing blackouts, including methods, metadata, and notifications.
seo-description: provides API elements that are useful when implementing blackouts, including methods, metadata, and notifications.
seo-title: Blackout API elements
title: Blackout API elements
---

# Blackout API elements

You can use the following when implementing a blackout solution in your player.
* **PTMediaPlayer**
    * `codeph registerCurrentItemAsBackgroundItem`
      Saves the currently loaded resource as the background resource. If `codeph replaceCurrentItemWithPlayerItem` is called after this method,  continues to download the background item’s manifest until you call `codeph unregisterCurrentBackgroundItem` , `codeph stop`, or `codeph reset` .
      
      
    * `codeph unregisterCurrentBackgroundItem`
      Sets the background item to nil and stops fetching and parsing the background manifest.
      
      
  
* **PTMetadata.PTBlackoutMetadata**
  A `codeph PTMetadata` class that is specific to blackouts.
  
  This allows you to set nonseekable ranges (an array of `codeph CMTimeRanges`) on .  checks for these ranges every time the user seeks. If it is set and the user seeks into a nonseekable range,  forces the viewer to the end of the nonseekable range.
  
  
* **START HERE NEXT** **PTAdMetadata**
  Enable or disable pre-roll on a live stream by setting `codeph enableLivePreroll` to YES or NO. If NO,  does not make an explicit ad server call for pre-roll ads before the content playback and so does not play the pre-roll. This has no impact on the mid-rolls. The default is YES.
  
  
* **NSNotifications**
    * `codeph PTTimedMetadataChangedInBackgroundNotification` - Posted when  detects a subscribed tag in the background manifest and a new `codeph PTTimedMetadata` instance is prepared from it. The notification’s object is the `codeph PTMediaPlayerItem` instance that is currently playing. You can fetch the `codeph PTTimedMetadata` instance from the notification's `codeph userInfo` dictionary using the `codeph PTTimedMetadataKey` key.
    * `codeph PTBackgroundManifestErrorNotification` - Posted when the media player completely fails to load the background manifest, that is, all of the stream URLs return either an error or an invalid response. The notification’s object is the `codeph PTMediaPlayerItem` instance that is currently playing.
  
* **PTNotification**
    * `codeph BACKGROUND_MANIFEST_WARNING`
        * Code: 204000
        * Type: Warning
        * Error in background manifest download.
      
    * `codeph INVALID_SEEK_WARNING`
      Dispatched when a seek is attempted in a nonseekable range (in `codeph nonSeekableRanges` set in `codeph PTBlackoutMetadata`).
      
      
  

