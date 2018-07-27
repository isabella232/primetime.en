---
description: This example shows the recommended way to include custom ad markers on the playback timeline.
seo-description: This example shows the recommended way to include custom ad markers on the playback timeline.
seo-title: Placing custom ad markers on the timeline
title: Placing custom ad markers on the timeline
uuid: 9b17df2e-06c5-43c3-af7c-5a5a58a27a82
index: n
internal: n
snippet: y
translate: y
---

# Placing custom ad markers on the timeline


>1. Translate the out-of-band ad-positioning information into a list/array of ` RepaceTimeRange` class.
>1. Create an instance of ` CustomRangeMetadata` class, and use its ` setTimeRangeList` method with the list/array as its argument to set its time range list.
>1. Use its ` setType` method to set the type to ` MARK_RANGE`.
>1. Use the ` MediaPlayerItemConfig.setCustomRangeMetadata` method with the ` CustomRangeMetadata` instance as its argument to set the custom range metadata.
>1. Use the ` MediaPlayer.replaceCurrentResource` method with the ` MediaPlayerItemConfig` instance as its argument to set make the new resource the current one.
>1. Wait for a ` STATE_CHANGED` event, which reports that the player is in the ` PREPARED` state.
>1. Start video playback by calling ` MediaPlayer.play`.
