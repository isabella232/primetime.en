---
description: The following changes in support ad deletion and replacement.
seo-description: The following changes in support ad deletion and replacement.
seo-title: Ad deletion and replacement API changes
title: Ad deletion and replacement API changes
---

# Ad deletion and replacement API changes

**New APIs**

* `codeph PTTimeRangeCollection` is a public class that defines a predefined set of ranges and a type:
    * `codeph property PTTimeRangeCollectionType type` indicates the type of time range.
    * `codeph property NSArray* ranges` is used to set the time ranges.
      The expected type of objects in the array are `codeph PTReplacementTimeRange` or `codeph CMTimeRange`.
      
      >[!TIP]
      >
      >All the objects of the array must be the same type.
      
    * `codeph PTTimeRangeCollectionType` is an enum that defines the behavior for the ranges that are defined in the `codeph PTTimeRangeCollection`:
        * `codeph PTTimeRangeCollectionTypeMarkRanges`: The type of the ranges is *Mark*. The ranges are used for marking the ranges in the content as Ads.
        * `codeph PTTimeRangeCollectionTypeDeleteRanges`: The type of the ranges is Delete. The defined ranges are removed from the main content before ad insertion.
        * `codeph PTTimeRangeCollectionTypeReplaceRanges`: The type of the ranges is Replace. The defined ranges are replaced from the main with Ads (Ad signaling mode is set to `codeph PTAdSignalingModeCustomTimeRanges`).
      
  
* `codeph PTReplacementTimeRange` - New public class that defines a single range of the `codeph PTTimeRangeCollection`:
    * `codeph property CMTimeRange range` - Defines the start and duration of the range.
    * `codeph property long replacementDuration` - If the type of the `codeph TimeRangeCollection` is `codeph PTTimeRangeCollectionTypeReplaceRanges`, the `codeph replacementDuration` is used to create a placement opportunity (ad insertion) with a duration of `codeph replacementDuration`. If the `codeph replacementDuration` is not set, the ad server will determine the duration and number of ads for that placement opportunity.
  
* `codeph PTAdSignalingMode`:
    * `codeph PTAdSignalingModeCustomTimeRanges` - Added a new type of `codeph PTAdSignalingMode`. This mode is used in conjunction with the `codeph PTTimeRangeCollection` with type `codeph PTTimeRangeCollectionReplace` for ad insertion based on the replacement ranges.
  
* `codeph PTAdMetadata`:
    * `codeph property PTTimeRangeCollection* timeRangeCollection` - For setting the time ranges used in the mark/delete/replace ranges in the playback content.
  
* Warning logs:
    * `codeph UNDEFINED_TIME_RANGES`
        * Type - Warning
        * Description - The ad signaling mode is defined as custom ranges but the custom ranges are not defined.
      
    * `codeph INVALID_TIME_RANGES`
        * Type - Warning
        * Description - One or more time ranges are invalid and will be ignored or modified.
      
  
**Deprecated APIs**

* `codeph PTAdMetadata`:
    * `codeph property NSArray* externalAdRanges` - This property was previously used to define C3 ranges for marking. It is now deprecated, as these ranges are set via `codeph PTTimeRangeCollection`.
  
