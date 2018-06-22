---
description: handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
seo-description: handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
seo-title: Ad deletion and replacement error handling
title: Ad deletion and replacement error handling
---

# Ad deletion and replacement error handling

deals with `codeph timeRanges` errors by doing default merging and reordering. First, it sorts customer-defined time ranges by the *begin* time. Based on this sorting order, it then merges adjacent ranges, and joins them if there are subsets and intersections among the ranges.

handles time-range errors as follows:
* Out of order -  reorders the time ranges.
* Subset -  merges the time-range subsets.
* Intersect -  merges the intersecting time ranges.
* Replace ranges conflict -  chooses the replace duration from the earliest appearing `codeph timeRange` in the conflicting group.

handles signaling-mode conflicts as follows:


* If REPLACE ranges are defined,  automatically changes the signaling mode to CUSTOM_RANGE.
* If DELETE ranges or MARK ranges are defined and the signaling mode is CUSTOM_RANGE,  deletes or marks these ranges. There is no ad insertion in this case.
* If a DELETE range or a MARK range defines a replacement duration,  ignores this duration.

When the server does not return valid `codeph AdBreaks`:
* generates and processes a `codeph NOPTimelineOperation` for the empty `codeph AdBreak`. No ad plays.

