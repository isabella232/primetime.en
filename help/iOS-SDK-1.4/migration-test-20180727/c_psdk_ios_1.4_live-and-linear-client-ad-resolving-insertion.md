---
description: supports several use cases for live and linear ad resolving and insertion.
seo-description: supports several use cases for live and linear ad resolving and insertion.
seo-title: Live and linear ad resolving and insertion
title: Live and linear ad resolving and insertion
uuid: 1e4f7750-d1fc-4c22-a38a-efe3d9f00078
index: n
internal: n
snippet: y
translate: y
---

# Live and linear ad resolving and insertion

 <!-- PH element: phrases/primetime-sdk-name --> supports the following live and linear use cases:
* Pre-roll ad insertion, where at least one ad is inserted at the beginning of the content.
* Mid-roll ad insertion, where at least one ad is inserted in the middle of the content.

<!-- PH element: phrases/primetime-sdk-name --> resolves the ads and inserts the ads when a cue point is encountered in the live or linear stream. By default, <!-- PH element: phrases/primetime-sdk-name --> supports the following cues as valid ad markers when resolving and placing ads:
* #EXT-X-CUEPOINT
* #EXT-X-AD
* #EXT-X-CUE
* #EXT-X-CUE-OUT

These markers require the metadata field's `DURATION` in seconds and the cue’s unique ID. For example: 
```
#EXT-X-CUE DURATION=27 ID=identiferForThisCue ...

```

For more information about additional cues, see [Subscribe to custom tags](t_psdk_ios_1.4_custom-tags-subscribe.md#t_psdk_ios_subscribing-to-custom-hls-tags). 
