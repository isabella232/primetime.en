---
description: The MediaPlayerItem.timedMetadata property provides access to all TimedMetadata objects that are created from playlist/manifest tags or from ID3 tags in the media stream.
seo-description: The MediaPlayerItem.timedMetadata property provides access to all TimedMetadata objects that are created from playlist/manifest tags or from ID3 tags in the media stream.
seo-title: Notifications for manifest tags
title: Notifications for manifest tags
uuid: 50727455-b37b-4e39-8efb-a97de3164074
---

# Notifications for manifest tags{#notifications-for-manifest-tags}

The MediaPlayerItem.timedMetadata property provides access to all TimedMetadata objects that are created from playlist/manifest tags or from ID3 tags in the media stream.

<!--<a id="section_9A22F6F1EA1F4F0C9E0C7687D12AA4AA"></a>-->

The `MediaPlayerItem.hasTimedMetadata` property indicates whether a subscribed custom tag exists in the current media. You can monitor timed metadata by listening for the `Events.TimedMetadataEvent`, which the MediaPlayer instance dispatches each time a new `TimedMetadata` object is created. 
