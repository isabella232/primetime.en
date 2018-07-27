---
description: The notifies your player client about the availability of internal AVAsset’s availableMediaCharacteristicsWithMediaSelectionOptions by using the PTMediaPlayerMediaSelectionOptionsAvailableNotification notification.
seo-description: The notifies your player client about the availability of internal AVAsset’s availableMediaCharacteristicsWithMediaSelectionOptions by using the PTMediaPlayerMediaSelectionOptionsAvailableNotification notification.
seo-title: Expose subtitles
title: Expose subtitles
uuid: 188f1844-9383-41e1-add8-5288cf6976f2
index: n
internal: n
snippet: y
translate: y
---

# Expose subtitles

You can access the available subtitles through the ` PTMediaPlayerItem` property's ` subtitlesOptions`. 
To expose subtitles:

>1. Register the client as a listener for the ` PTMediaPlayerMediaSelectionOptionsAvailableNotification` notification.
>
>   ```
>   [[NSNotificationCenter defaultCenter]  
>     addObserver:self selector:@selector(onMediaPlayerItemMediaSelectionOptionsAvailable:)  
>     name:PTMediaPlayerMediaSelectionOptionsAvailableNotification object:self.player];
>   ```
>   When your client receives this notification, the subtitles are ready in the ` PTMediaPlayerItem`.>
>1. Implement the ` onMediaPlayerItemMediaSelectionOptionsAvailable` method similar to the following example:
>
>   ```
>   - (void) onMediaPlayerItemMediaSelectionOptionsAvailable:(NSNotification *) notification { 
>       NSArray* subtitlesOptions = self.player.currentItem.subtitlesOptions; 
>       NSArray* audioOptions = self.player.currentItem.audioOptions; 
>   }
>   ```
>
>   For information about alternate audio tracks, see  alternate-audio . 
>
