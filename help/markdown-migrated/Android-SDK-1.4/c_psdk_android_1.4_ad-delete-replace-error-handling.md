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

handles signaling-mode conflicts with ad metadata as follows:


* If the ad signaling mode conflicts with the time-range metadata, the time-range metadata always has priority. For example, if the ad signaling mode is set as server map or manifest cues, and there are also MARK time ranges in the ad metadata, the resulting behavior is that the ranges are marked, and no ads are inserted.
* For REPLACE ranges, if the signaling mode is set as server map or manifest cues, the ranges are replaced as specified in the REPLACE ranges, and there is no ad insertion through server map or manifest cues. See []().

When the server does not return valid `codeph AdBreaks`:
* generates and processes a `codeph NOPTimelineOperation` for the empty `codeph AdBreak`. No ad plays.

For time ranges with live streams:
* Although this C3 ad delete/replacement feature is intended to be supported only for VOD, time ranges are processed for live streams as well if specified in the ad metadata.

