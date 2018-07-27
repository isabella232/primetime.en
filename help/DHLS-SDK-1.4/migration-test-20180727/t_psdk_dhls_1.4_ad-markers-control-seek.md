---
description: You can override the default behavior for how seeks over ads when using custom ad markers.
seo-description: You can override the default behavior for how seeks over ads when using custom ad markers.
seo-title: Control playback behavior for seeking over custom ad markers
title: Control playback behavior for seeking over custom ad markers
uuid: 37579c03-aaa9-4b07-8af1-1c456670d442
index: n
internal: n
snippet: y
translate: y
---

# Control playback behavior for seeking over custom ad markers

By default, when a user seeks into or past ad sections that result from the placement of custom ad markers,  <!-- PH element: phrases/primetime-sdk-name --> skips the ads. This might differ from the current playback behavior for standard ad breaks.
You can tell  <!-- PH element: phrases/primetime-sdk-name --> to reposition the playhead to the beginning of the most recently skipped custom ad when the user seeks past one or more custom ads.

>1. Configure a Metadata instance with the `DefaultMetadataKeys.METADATA_KEY_ADJUST_SEEK_ENABLED` enumeration set to the string value "true" (not as a Boolean `true`).
>
>1. Create and configure a `MediaResource` instance, passing the additional configuration options to `TimeRangeCollection.toMetadata`. This method receives additional configuration options via another generic metadata structure.

>
