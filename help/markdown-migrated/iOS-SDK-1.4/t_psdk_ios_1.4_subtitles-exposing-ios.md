---
description: The notifies your player client about the availability of internal AVAsset’s availableMediaCharacteristicsWithMediaSelectionOptions by using the PTMediaPlayerMediaSelectionOptionsAvailableNotification notification.
seo-description: The notifies your player client about the availability of internal AVAsset’s availableMediaCharacteristicsWithMediaSelectionOptions by using the PTMediaPlayerMediaSelectionOptionsAvailableNotification notification.
seo-title: Expose subtitles
title: Expose subtitles
---

# Expose subtitles

You can access the available subtitles through the `codeph  PTMediaPlayerItem` property's `codeph  subtitlesOptions`.

To expose subtitles:

>1. Register the client as a listener for the `codeph  PTMediaPlayerMediaSelectionOptionsAvailableNotification` notification.
>   ```
>   [[NSNotificationCenter defaultCenter] 
>    addObserver:self selector:@selector(onMediaPlayerItemMediaSelectionOptionsAvailable:) 
>    name:PTMediaPlayerMediaSelectionOptionsAvailableNotification object:self.player];
>   ```
>   When your client receives this notification, the subtitles are ready in the`codeph  PTMediaPlayerItem`.
>   
>1. Implement the `codeph  onMediaPlayerItemMediaSelectionOptionsAvailable` method similar to the following example:
>   ```
>   - (void) onMediaPlayerItemMediaSelectionOptionsAvailable:(NSNotification *) notification { 
>    NSArray* subtitlesOptions = self.player.currentItem.subtitlesOptions; 
>    NSArray* audioOptions = self.player.currentItem.audioOptions; 
>   }
>   ```
>   
>   For information about alternate audio tracks, see [ Alternate Audio ]().
>   
>   
>   
>   
