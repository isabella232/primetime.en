---
description: TVSDK handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
seo-description: TVSDK handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
seo-title: Ad deletion and replacement error handling
title: Ad deletion and replacement error handling
uuid: 3715ac91-d969-44fc-818a-966d0727fee6
index: y
internal: n
snippet: y
---

# Ad deletion and replacement error handling{#ad-deletion-and-replacement-error-handling}

TVSDK handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.

TVSDK deals with `timeRanges` errors by doing default merging and reordering. First, it sorts customer-defined time ranges by the *begin* time. Based on this sorting order, it then merges adjacent ranges, and joins them if there are subsets and intersections among the ranges.

TVSDK handles time-range errors as follows:

* Out of order - TVSDK reorders the time ranges. 
* Subset - TVSDK merges the time-range subsets. 
* Intersect - TVSDK merges the intersecting time ranges. 
* Replace ranges conflict - TVSDK chooses the replace duration from the earliest appearing `timeRange` in the conflicting group.

TVSDK handles signaling-mode conflicts as follows:

* If REPLACE ranges are defined, TVSDK automatically changes the signaling mode to CUSTOM_RANGE. 
* If DELETE ranges or MARK ranges are defined and the signaling mode is CUSTOM_RANGE, TVSDK deletes or marks these ranges. There is no ad insertion in this case. 
* If a DELETE range or a MARK range defines a replacement duration, TVSDK ignores this duration.

When the server does not return valid `AdBreaks`:

* TVSDK generates and processes a `NOPTimelineOperation` for the empty `AdBreak`. No ad plays.

