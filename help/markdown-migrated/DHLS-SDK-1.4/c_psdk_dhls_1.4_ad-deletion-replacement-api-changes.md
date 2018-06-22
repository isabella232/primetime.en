---
description: These changes in support ad deletion and replacement.
seo-description: These changes in support ad deletion and replacement.
seo-title: Ad deletion and replacement API changes
title: Ad deletion and replacement API changes
---

# Ad deletion and replacement API changes

* `codeph  AdSignalingMode`
  Added `codeph  CUSTOM_RANGES` signaling mode.
  
  
* `codeph  OpportunityGenerator`
  `codeph  extractAdSignalingMode()` - Set `codeph  AdSignalingMode.CUSTOM_RANGES` if replace ranges are in the metadata.
  
  
* `codeph  PlacementType`
  Added `codeph  CUSTOM_RANGE` type.
  
  
* `codeph  PlacementMode`
    * Added `codeph  DELETE` mode.
    * Added `codeph  MARK` mode
    * Added `codeph  FreeReplace` mode - This mode has a duration but is a pure insertion
  
* `codeph  TimeRange`
  No longer a `codeph  final` class
  
  
* Added `codeph  ReplaceTimeRange()` method
  Extends `codeph  TimeRange` to have a `codeph  replacementDuration` property. For the MARK and DELETE cases, `codeph  replacementDuration` is 0.
  
  
* `codeph  TimeRangeCollection`
    * Added `codeph  toReplaceMetadata()` utility function to extract `codeph  timeRanges`.
    * Modified to work with `codeph  DELETE` and `codeph  REPLACE`
    * `codeph  METADATA_KEY_CUSTOM_MARK_RANGES`, `codeph  METADATA_KEY_CUSTOM_DELETE_RANGES`, `codeph  METADATA_KEY_CUSTOM_REPLACE_RANGES`
  
* `codeph  CatalogItem`
    * Added `codeph  createCustomTimeRangesFrom()` - Creates metadata for MARK/DELETE/REPLACE use cases from the JSON file.
    * Removed `codeph  createCustomAdMarkersMetadataFrom()`
  
* `codeph  DefaultMetadataKeys`
    * Added `codeph  CUSTOM_DELETE_RANGES_METADATA_KEY`
    * Added `codeph  CUSTOM_REPLACE_RANGES_METADATA_KEY`
    * `codeph  CUSTOM_AD_MARKERS_METADATA_KEY` (did not change)
  
* `codeph  DefaultContentFactory`
    * `codeph  doRetrieveGenerators()`
        * Added `codeph  CustomRangesOpportunityGenerator` for when the metadata contains custom ranges
      
    * `codeph  doRetrieveResolvers()`
        * Add `codeph  CustomRangeResolver` for when DELETE and REPLACE custom ranges are present in the metadata
        * Moved `codeph  CustomAdMarkerResolver` ahead of `codeph  AuditudeResolver`
      
  
* Added `codeph  CustomRangeOpportunityGenerator`
    * `codeph  doUpdate()` Leaves empty - no Update, VOD
    * `codeph  doProcess()` Creates a new placement of a new type `codeph  Placement.Delete_Range`
    * Added `codeph  CustomRangeOppotunityGenerator` to the top of the generators list in `codeph  DefaultContentFactory`, so delete ranges are processed before ad insertions.
    * Added `codeph  createCustomRangeOpportunities` to create all the opportunities
      MARK - One opportunity for each valid mark range of `codeph  PlacementType.CUSTOM_RANGE` and `codeph  PlacementMode.MARK`
      
      DELETE - One opportunity for each valid delete range of `codeph  PlacementType.CUSTOM_RANGE` and `codeph  PlacementMode.DELETE`
      
      REPLACE - Two opportunities for each valid replace range:
        1. A delete range opportunity of `codeph  PlacementType.CUSTOM_RANGE` and `codeph  PlacementMode.DELETE`.
        1. An  ad opportunity of `codeph  PlacementType.MID_ROLL` or `codeph  PlacementType.PRE_ROLL` and `codeph  PlacementMode.FREEREPLACE`
      
      
  
* Added `codeph  CustomRangeResolver`:
    * `codeph  doCanResolve()` returns `codeph  true` for delete ranges.
    * Added `codeph  createDeleteRangeOperation()` to create `codeph  DeleteRange` for the placement
  
* Added `codeph  CustomRangeHelper`:
    * Common utility class to extract Mark/Delete/Replace `codeph  timeRanges` and process them.
    * Added `codeph  extractCustomRangesMetadata()`
    * Added `codeph  extractCustomRanges()`
    * Added `codeph  mergeRanges()` - Resolves conflicts and subsets/merges
  
* `codeph  MediaPlayerTimeline`:
    * "&gt;In `codeph  executeOperation()`, if the operation is `codeph  DeleteRange`, added call to remove method in the operation
    * In `codeph  executeOperation()`, if the operation is `codeph  NOPTimelineOperation` (empty `codeph  AdBreaks` coming back from server), added call to clear.
    * Added `codeph  onDeleteRangeComplete()`
    * Added `codeph  removeRange()`
    * In `codeph  adjustPlacement()`, for `codeph  PlacementMode.FREEREPLACE` mode, zeroed out the duration. This duration is needed earlier when requesting `codeph  AdBreaks`, at this point it needs to be zero to be pure insertion.
  
* `codeph  VideoEngineTimeline`
  Added `codeph  removeC3Ad()` - call `codeph  removeByLocalTime()` for delete ranges
  
  
* `codeph  AdSignalingModeGenerator`
    * `codeph  doConfigure()` - Do not resolve if no opportunity is generated
    * `codeph  createInitialOpportunity()` - Do not generate initial opportunity for `codeph  AdSignalingMode.CUSTOM_RANGE`. The `codeph  CustomRangeOpportunityGenerator` covers this already.
  
* `codeph  DeleteRange`
    * Extends `codeph  TimelineOperation`.
    * Created by `codeph  CustomRangeResolver` for delete and replacement (the deletion part of replacement)
  
* `codeph  AuditudeConstant`
    * `codeph  MAX_PLACEMENTS_PER_REQUEST 1-&gt;5` - allow packing
    * `codeph  MINIMUM_AD_DURATION 10-&gt;5`
  
* `codeph  AuditudeRequest`
  The `codeph  accepts()` method was modified to allow packing of different placement type (pre-roll, mid-roll, post-roll)
  
  
* `codeph  AuditudeRequestHelper`
  Bug fixes to allow server override of Ad parameters
  
  
* `codeph  AuditudeResolver`
  The `codeph  canBePacked()` method was changed to allow packing
  
  
* `codeph  CustomAdResolver`
  The `codeph  timeRange` extraction functions have been removed. We get one placement at a time, and turn that into a `codeph  AdBreakPlacement timelineOperation`.
  
  
