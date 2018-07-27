---
description: handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
seo-description: handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
seo-title: Ad deletion and replacement error handling
title: Ad deletion and replacement error handling
uuid: d7f15e5b-1d5b-4055-abec-5ac143f0a5f1
index: n
internal: n
snippet: y
translate: y
---

# Ad deletion and replacement error handling

 <!-- PH element: phrases/primetime-sdk-name --> deals with `timeRanges` errors by doing default merging and reordering. First, it sorts customer-defined time ranges by the *begin* time. Based on this sorting order, it then merges adjacent ranges, and joins them if there are subsets and intersections among the ranges.
<!-- PH element: phrases/primetime-sdk-name --> handles time-range errors as follows:
* Out of order -  <!-- PH element: phrases/primetime-sdk-name --> reorders the time ranges.
* Subset -  <!-- PH element: phrases/primetime-sdk-name --> merges the time-range subsets.
* Intersect -  <!-- PH element: phrases/primetime-sdk-name --> merges the intersecting time ranges.
* Replace ranges conflict -  <!-- PH element: phrases/primetime-sdk-name --> chooses the replace duration from the earliest appearing `timeRange` in the conflicting group.

<!-- PH element: phrases/primetime-sdk-name --> handles signaling-mode conflicts as follows:

* If REPLACE ranges are defined,  <!-- PH element: phrases/primetime-sdk-name --> automatically changes the signaling mode to CUSTOM_RANGE.
* If DELETE ranges or MARK ranges are defined and the signaling mode is CUSTOM_RANGE,  <!-- PH element: phrases/primetime-sdk-name --> deletes or marks these ranges. There is no ad insertion in this case.
* If a DELETE range or a MARK range defines a replacement duration,  <!-- PH element: phrases/primetime-sdk-name --> ignores this duration.

When the server does not return valid `AdBreaks`: 
* <!-- PH element: phrases/primetime-sdk-name --> generates and processes a `NOPTimelineOperation` for the empty `AdBreak`. No ad plays.

