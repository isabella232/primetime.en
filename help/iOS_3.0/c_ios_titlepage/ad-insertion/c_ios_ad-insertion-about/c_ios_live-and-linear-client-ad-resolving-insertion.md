---
description: TVSDK supports several use cases for live and linear ad resolving and insertion.
seo-description: TVSDK supports several use cases for live and linear ad resolving and insertion.
seo-title: Live and linear ad resolving and insertion
title: Live and linear ad resolving and insertion
uuid: acbe217b-d5e1-4c07-be5d-9268b3cc87bb
index: y
internal: n
snippet: y
translate: y
---

# Live and linear ad resolving and insertion

TVSDK supports several use cases for live and linear ad resolving and insertion.

TVSDK supports the following live and linear use cases: 
* Pre-roll ad insertion, where at least one ad is inserted at the beginning of the content.* Mid-roll ad insertion, where at least one ad is inserted in the middle of the content.



TVSDK resolves the ads and inserts the ads when a cue point is encountered in the live or linear stream. By default, TVSDK supports the following cues as valid ad markers when resolving and placing ads: 
* #EXT-X-CUEPOINT* #EXT-X-AD* #EXT-X-CUE* #EXT-X-CUE-OUT



These markers require the metadata field's `DURATION` in seconds and the cue’s unique ID. For example: 
```
#EXT-X-CUE DURATION=27 ID=identiferForThisCue ...

```


For more information about additional cues, see [Subscribe to custom tags](../../../c_ios_titlepage/ad-insertion/c_ios_custom-tags-configure/t_ios_custom-tags-subscribe.md#t_psdk_ios_subscribing-to-custom-hls-tags). 
