---
description: inserts the alternate content (ads) into the timeline that corresponds to the main content.
seo-description: inserts the alternate content (ads) into the timeline that corresponds to the main content.
seo-title: Ad-insertion phase
title: Ad-insertion phase
uuid: 92ae4c1f-813f-410f-a2cb-c000473ba1cd
index: n
internal: n
snippet: y
translate: y
---

# Ad-insertion phase

When the ad-resolving phase is complete,  <!-- PH element: phrases/primetime-sdk-name --> has an ordered list of ad resources that are grouped into ad breaks. Each ad break is positioned on the main content timeline using a start-time value that is expressed in milliseconds (ms). Each ad in an ad break has a duration property that is also expressed in ms. The ads in an ad break are chained together one after another. As a result, the duration of an ad break is equal to the sum of the durations of the individual composing ads.
Failover can occur in this phase with conflicts that might occur on the timeline during ad insertion. For specific combinations of ad break start-time/duration values, ad segments might overlap. The overlap occurs when the last portion of an ad break intersects the beginning of the first ad in the next ad break. In these situations,  <!-- PH element: phrases/primetime-sdk-name --> discards the later ad break and continues the ad-insertion process with the next item on the list until all ad breaks are inserted or discarded.
<!-- PH element: phrases/primetime-sdk-name --> issues a warning notification about the error and continues processing.
