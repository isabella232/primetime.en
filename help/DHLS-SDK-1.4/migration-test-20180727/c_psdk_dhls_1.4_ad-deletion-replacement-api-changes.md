---
description: These changes in support ad deletion and replacement.
seo-description: These changes in support ad deletion and replacement.
seo-title: Ad deletion and replacement API changes
title: Ad deletion and replacement API changes
uuid: 1d6c7409-29e7-407f-bdd9-26cf5578ec3d
index: n
internal: n
snippet: y
translate: y
---

# Ad deletion and replacement API changes


* ` AdSignalingMode` Added ` CUSTOM_RANGES` signaling mode.

* ` OpportunityGenerator` ` extractAdSignalingMode()` -Set ` AdSignalingMode.CUSTOM_RANGES` if replace rangesare in the metadata.

* ` PlacementType` Added ` CUSTOM_RANGE` type.

* ` PlacementMode` 
    * Added ` DELETE` mode.
    * Added ` MARK` mode
    * Added ` FreeReplace` mode- This mode has a duration but is a pure insertion

* ` TimeRange` Nolonger a ` final` class

* Added ` ReplaceTimeRange()` method Extends ` TimeRange` tohave a ` replacementDuration` property. For the MARKand DELETE cases, ` replacementDuration` is 0.

* ` TimeRangeCollection` 
    * Added ` toReplaceMetadata()` utilityfunction to extract ` timeRanges`.
    * Modified to workwith ` DELETE` and ` REPLACE`
    * ` METADATA_KEY_CUSTOM_MARK_RANGES`, ` METADATA_KEY_CUSTOM_DELETE_RANGES`, ` METADATA_KEY_CUSTOM_REPLACE_RANGES`

* ` CatalogItem` 
    * Added ` createCustomTimeRangesFrom()` - Createsmetadata for MARK/DELETE/REPLACE use cases from the JSON file.
    * Removed ` createCustomAdMarkersMetadataFrom()`

* ` DefaultMetadataKeys` 
    * Added ` CUSTOM_DELETE_RANGES_METADATA_KEY`
    * Added ` CUSTOM_REPLACE_RANGES_METADATA_KEY`
    * ` CUSTOM_AD_MARKERS_METADATA_KEY` (didnot change)

* ` DefaultContentFactory` 
    * ` doRetrieveGenerators()`     
        * Added ` CustomRangesOpportunityGenerator` forwhen the metadata contains custom ranges

    * ` doRetrieveResolvers()`     
        * Add ` CustomRangeResolver` forwhen DELETE and REPLACE custom ranges are present in the metadata
        * Moved ` CustomAdMarkerResolver` aheadof ` AuditudeResolver`


* Added ` CustomRangeOpportunityGenerator` 
    * ` doUpdate()` Leavesempty - no Update, VOD
    * ` doProcess()` Createsa new placement of a new type ` Placement.Delete_Range`
    * Added ` CustomRangeOppotunityGenerator` tothe top of the generators list in ` DefaultContentFactory`,so delete ranges are processed before ad insertions.
    * Added ` createCustomRangeOpportunities` tocreate all the opportunities MARK - One opportunity for eachvalid mark range of ` PlacementType.CUSTOM_RANGE` and ` PlacementMode.MARK`
      DELETE- One opportunity for each valid delete range of ` PlacementType.CUSTOM_RANGE` and ` PlacementMode.DELETE`
      REPLACE- Two opportunities for each valid replace range:     
        1. A delete range opportunityof ` PlacementType.CUSTOM_RANGE` and ` PlacementMode.DELETE`.
        1. An  <!-- PH element: phrases/auditude-name --> adopportunity of ` PlacementType.MID_ROLL` or ` PlacementType.PRE_ROLL` and ` PlacementMode.FREEREPLACE`



* Added ` CustomRangeResolver`: 
    * ` doCanResolve()` returns ` true` fordelete ranges.
    * Added ` createDeleteRangeOperation()` tocreate ` DeleteRange` for the placement

* Added ` CustomRangeHelper`: 
    * Common utility classto extract Mark/Delete/Replace ` timeRanges` and processthem.
    * Added ` extractCustomRangesMetadata()`
    * Added ` extractCustomRanges()`
    * Added ` mergeRanges()` - Resolvesconflicts and subsets/merges

* ` MediaPlayerTimeline`: 
    * "&gt;In ` executeOperation()`, ifthe operation is ` DeleteRange`, added call to removemethod in the operation
    * In ` executeOperation()`,if the operation is ` NOPTimelineOperation` (empty ` AdBreaks` comingback from server), added call to clear.
    * Added ` onDeleteRangeComplete()`
    * Added ` removeRange()`
    * In ` adjustPlacement()`,for ` PlacementMode.FREEREPLACE` mode, zeroed outthe duration. This duration is needed earlier when requesting ` AdBreaks`,at this point it needs to be zero to be pure insertion.

* ` VideoEngineTimeline` Added ` removeC3Ad()` -call ` removeByLocalTime()` for delete ranges

* ` AdSignalingModeGenerator` 
    * ` doConfigure()` -Do not resolve if no opportunity is generated
    * ` createInitialOpportunity()` - Donot generate initial opportunity for ` AdSignalingMode.CUSTOM_RANGE`. The ` CustomRangeOpportunityGenerator` coversthis already.

* ` DeleteRange` 
    * Extends ` TimelineOperation`.
    * Created by ` CustomRangeResolver` fordelete and replacement (the deletion part of replacement)

* ` AuditudeConstant` 
    * ` MAX_PLACEMENTS_PER_REQUEST 1-&gt;5` -allow packing
    * ` MINIMUM_AD_DURATION 10-&gt;5`

* ` AuditudeRequest` The ` accepts()` methodwas modified to allow packing of different placement type (pre-roll,mid-roll, post-roll)

* ` AuditudeRequestHelper` Bugfixes to allow server override of Ad parameters

* ` AuditudeResolver` The ` canBePacked()` methodwas changed to allow packing

* ` CustomAdResolver` The ` timeRange` extractionfunctions have been removed. We get one placement at a time, andturn that into a ` AdBreakPlacement timelineOperation`.

