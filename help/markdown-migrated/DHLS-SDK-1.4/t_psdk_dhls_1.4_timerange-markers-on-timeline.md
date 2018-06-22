---
description: This example shows the recommended way to include TimeRange specifications on the playback timeline.
seo-description: This example shows the recommended way to include TimeRange specifications on the playback timeline.
seo-title: Place TimeRange ad markers on the timeline
title: Place TimeRange ad markers on the timeline
---

# Place TimeRange ad markers on the timeline

>1. Translate the out-of-band ad-positioning information into a list of `codeph  TimeRange` specifications (that is, instances of the `codeph  TimeRange` class).
>   
>1. Use the set of `codeph  TimeRange` specifications to populate an instance of the `codeph  TimeRangeCollection` class.
>   
>1. Pass the Metadata instance, which can be obtained from the `codeph  TimeRangeCollection` instance, to the `codeph  replaceCurrentItem` method (part of the `codeph  MediaPlayer` interface).
>   
>1. Wait for  to transition to the PREPARED state by waiting for the `codeph  PlaybackEventListener#onPrepared` callback to be triggered.
>   
>1. Start video playback by calling the `codeph  play()` method (part of the `codeph  MediaPlayer` interface).
>   
>   
