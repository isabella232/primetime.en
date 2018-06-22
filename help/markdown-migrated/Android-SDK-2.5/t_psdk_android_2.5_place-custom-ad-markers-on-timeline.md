---
description: This example shows the recommended way to include custom ad markers on the playback timeline.
seo-description: This example shows the recommended way to include custom ad markers on the playback timeline.
seo-title: Placing custom ad markers on the timeline
title: Placing custom ad markers on the timeline
---

# Placing custom ad markers on the timeline

>1. Translate the out-of-band ad-positioning information into a list/array of `codeph  RepaceTimeRange` class.
>   
>1. Create an instance of `codeph  CustomRangeMetadata` class, and use its `codeph  setTimeRangeList` method with the list/array as its argument to set its time range list.
>   
>1. Use its `codeph  setType` method to set the type to `codeph  MARK_RANGE`.
>   
>1. Use the `codeph  MediaPlayerItemConfig.setCustomRangeMetadata` method with the `codeph  CustomRangeMetadata` instance as its argument to set the custom range metadata.
>   
>1. Use the `codeph  MediaPlayer.replaceCurrentResource` method with the `codeph  MediaPlayerItemConfig` instance as its argument to set make the new resource the current one.
>   
>1. Wait for a `codeph  STATE_CHANGED` event, which reports that the player is in the `codeph  PREPARED` state.
>   
>1. Start video playback by calling `codeph  MediaPlayer.play`.
>   
>   
