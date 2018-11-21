---
description: The MediaPlayerItem.timedMetadata property provides access to all TimedMetadata objects that are created from playlist/manifest tags or from ID3 tags in the media stream.
seo-description: The MediaPlayerItem.timedMetadata property provides access to all TimedMetadata objects that are created from playlist/manifest tags or from ID3 tags in the media stream.
seo-title: Notifications for manifest tags
title: Notifications for manifest tags
uuid: 75b7f2d4-c717-4477-870e-ade8c007c204
index: y
internal: n
snippet: y
---

# Notifications for manifest tags{#notifications-for-manifest-tags}

The MediaPlayerItem.timedMetadata property provides access to all TimedMetadata objects that are created from playlist/manifest tags or from ID3 tags in the media stream.

<a id="section_9A22F6F1EA1F4F0C9E0C7687D12AA4AA"></a>

The `MediaPlayerItem.hasTimedMetadata` property indicates whether a subscribed custom tag exists in the current media. You can monitor timed metadata by listening for the `Events.TimedMetadataEvent`, which the MediaPlayer instance dispatches each time a new `TimedMetadata` object is created. 
