---
description: The MediaPlayerItem.timedMetadata property gives you access to all the TimedMetadata objects created from playlist/manifest tags or from ID3 tags within the media stream. The MediaPlayerItem.hasTimedMetadata property indicates whether a subscribed custom tag is present in the current media. Q: To do-- I got this Short Description paragraph too late to check on the names of these things for Android and iOS. Come back later and figure it out, or ask.
seo-description: The MediaPlayerItem.timedMetadata property gives you access to all the TimedMetadata objects created from playlist/manifest tags or from ID3 tags within the media stream. The MediaPlayerItem.hasTimedMetadata property indicates whether a subscribed custom tag is present in the current media. Q: To do-- I got this Short Description paragraph too late to check on the names of these things for Android and iOS. Come back later and figure it out, or ask.
seo-title: Notifications for manifest tags
title: Notifications for manifest tags
uuid: 0117b563-5ef4-44a3-ad23-ab747a2d1bf7
index: n
internal: n
snippet: y
translate: y
---

# Notifications for manifest tags

<!-- WRITER: The DHLS version following is newer and probably more useful, but didn't have time to figure out the equivalent Android &amp; iOS version, so left them as they were for now. (1.3) Also didn't have time to figure out where to put the possibly-useful DHLS references within the Android/iOS version (that now won't appear int he doc). --> You can monitor timed metadata by listening for the following events, which notify your application of related activity: 
* MediaPlayerItemEvent.ITEM_CREATED: The initial list of TimedMetadata objects is available after the MediaPlayerItem is created. This event notifies your application when this happens.
* MediaPlayerItemEvent.ITEM_UPDATED: For live/linear streams where the manifest/playlist refreshes periodically, additional custom tags might appear in the updated playlist/manifest, so additional TimedMetadata objects might be added to the MediaPlayerItem.timedMetadata property. This event notifies your application when this happens.
* TimedMetadataEvent.TIMED_METADATA_AVAILABLE: Every time that a new TimedMetadata object is created, this event is dispatched by the MediaPlayer. This event is not dispatched for the TimedMetadata object created during the initialization phase.

The event ` MediaPlayer.PlaybackEventListener.onTimedMetadata` ` events.TimedMetadataEvent` ` PTTimedMetadataChangedNotification` notifies your application at the first occurrence in the manifest of each tag that matches a subscribed tag name. <!-- Q: I guessed about the DHLS event. --> 
When the  encounters the first occurrence of a subscribed tag in the ` m3u8` playlist, it creates a new ` TimedMetadata` ` PTTimedMetadata` object for this tag. 
The ` MediaPlayerItem.hasTimedMetadata` indicates when this information is available, and you can retrieve it with ` MediaPlayerItem.getTimedMetadata`. <!-- Q: The iOS version says this; what's the equivalent for Android? "The PTTimedMetadata is added to the timedMetadataCollection in PTMediaPlayerItem and the 
<ph conref="phrase_library_ios.xml#c_psdk_phrase-library/primetime-sdk-name">
  Phrase 
</ph> issues a PTTimedMetadataChangedNotification notification and includes this new object in the notification’s userInfo dictionary." --> 
The ` PTTimedMetadata` is added to the ` timedMetadataCollection` in ` PTMediaPlayerItem` and the  issues a ` PTTimedMetadataChangedNotification` notification and includes this new object in the notification’s ` userInfo` dictionary. 
