---
description: This example shows the recommended way to include TimeRange specifications on the playback timeline.
seo-description: This example shows the recommended way to include TimeRange specifications on the playback timeline.
seo-title: Place TimeRange ad markers on the timeline
title: Place TimeRange ad markers on the timeline
uuid: 9a087541-8c84-4ced-8572-54124fe2676b
index: n
internal: n
snippet: y
translate: y
---

# Place TimeRange ad markers on the timeline


>1. Translate the out-of-band ad-positioning information into a list of ` TimeRange` specifications (that is, instances of the ` TimeRange` class).
>1. Use the set of ` TimeRange` specifications to populate an instance of the ` TimeRangeCollection` class.
>1. Pass the Metadata instance, which can be obtained from the ` TimeRangeCollection` instance, to the ` replaceCurrentItem` method (part of the MediaPlayer interface).
>1. Wait for  <!-- PH element: phrases/primetime-sdk-name --> to transition to the ` PREPARED` state by waiting for the ` PlaybackEventListener#onPrepared` callback to be triggered.
>1. Start video playback by calling the ` play()` method (part of the ` MediaPlayer` interface).
