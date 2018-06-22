---
description: The MediaPlayerItem.timedMetadata property gives you access to all the TimedMetadata objects created from playlist/manifest tags or from ID3 tags within the media stream. The MediaPlayerItem.hasTimedMetadata property indicates whether a subscribed custom tag is present in the current media.
seo-description: The MediaPlayerItem.timedMetadata property gives you access to all the TimedMetadata objects created from playlist/manifest tags or from ID3 tags within the media stream. The MediaPlayerItem.hasTimedMetadata property indicates whether a subscribed custom tag is present in the current media.
seo-title: Notifications for manifest tags
title: Notifications for manifest tags
---

# Notifications for manifest tags

You can monitor timed metadata by listening for the following events, which notify your application of related activity:
* `codeph MediaPlayerItemEvent.ITEM_CREATED`: The initial list of `codeph TimedMetadata` objects is available after the `codeph MediaPlayerItem` is created. This event notifies your application when this happens.
* `codeph MediaPlayerItemEvent.ITEM_UPDATED`: For live/linear streams where the manifest/playlist refreshes periodically, additional custom tags might appear in the updated playlist/manifest, so additional TimedMetadata objects might be added to the `codeph MediaPlayerItem.timedMetadata` property. This event notifies your application when this happens.
* `codeph TimedMetadataEvent.TIMED_METADATA_AVAILABLE`: Every time that a new `codeph TimedMetadata` object is created, this event is dispatched by the `codeph MediaPlayer`. This event is not dispatched for the `codeph TimedMetadata` object created during the initialization phase.

