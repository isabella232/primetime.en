---
description: TVSDK handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
seo-description: TVSDK handles time range errors according to the specific problem, either merging or reordering the improperly defined time ranges.
seo-title: Ad deletion and replacement error handling
title: Ad deletion and replacement error handling
uuid: fc745771-d06d-48bf-a416-8115408839f0
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

TVSDK handles signaling-mode conflicts with ad metadata as follows:

* If the ad signaling mode conflicts with the time-range metadata, the time-range metadata always has priority. For example, if the ad signaling mode is set as server map or manifest cues, and there are also MARK time ranges in the ad metadata, the resulting behavior is that the ranges are marked, and no ads are inserted.
* For REPLACE ranges, if the signaling mode is set as server map or manifest cues, the ranges are replaced as specified in the REPLACE ranges, and there is no ad insertion through server map or manifest cues. See  ad-signaling-mode .

When the server does not return valid `AdBreaks`:

* TVSDK generates and processes a `NOPTimelineOperation` for the empty `AdBreak`. No ad plays.

For time ranges with live streams:

* Although this C3 ad delete/replacement feature is intended to be supported only for VOD, time ranges are processed for live streams as well if specified in the ad metadata.

