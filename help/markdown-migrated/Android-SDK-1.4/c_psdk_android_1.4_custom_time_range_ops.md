---
description: Ad deletion and replacement is implemented with TimeRange elements that identify different types of time ranges in a VOD stream: mark, delete, and replace. For each of these custom time range types, you can perform corresponding operations, including deleting and replacing ad content.
seo-description: Ad deletion and replacement is implemented with TimeRange elements that identify different types of time ranges in a VOD stream: mark, delete, and replace. For each of these custom time range types, you can perform corresponding operations, including deleting and replacing ad content.
seo-title: Custom time range operations
title: Custom time range operations
---

# Custom time range operations


For ad deletion and replacement,  uses the following *custom time range operation* modes:
* MARK
  (These were referred to as custom ad markers in previous versions of ). They mark the beginning and ending times for ads that are already placed into the VOD stream. When there are time range markers of type MARK in the stream, an initial placement of `codeph Mode.MARK` is generated and resolved by the `codeph CustomAdMarkersContentResolver`. No ads are inserted.
  
  
* DELETE
  For DELETE time ranges, an initial `codeph placementInformation` of type `codeph Mode.DELETE` is created and resolved by the corresponding `codeph DeleteContentResolver`. `codeph ContentRemoval` is a new `codeph timelineOperation` that defines the ranges to be removed from the timeline.  uses `codeph removeByLocalTime` from the Adobe Video Engine (AVE) API to facilitate that operation. If there are DELETE ranges and  (previously known as ) metadata, the ranges are deleted first, then the `codeph AuditudeResolver` resolves ads using the normal  workflow.
  
  
* REPLACE
  For REPLACE time ranges, two initial `codeph placementInformations` are created, one `codeph Mode.DELETE` and one `codeph Mode.REPLACE`. The `codeph DeleteContentResolver` deletes the time ranges first and then the `codeph AuditudeResolver` inserts ads of the specified `codeph replaceDuration` into the timeline. If no `codeph replaceDuration` is specified, the server determines what to insert.
  
  

To support these custom time range operations,  provides the following:
* Multiple content resolvers
  A stream can have multiple content resolvers based on the ad signaling mode and ad metadata. The behavior changes with different combinations of ad signaling modes and ad metadata.
  
  
* Multiple initial `codeph PlacementInformations`
  The `codeph DefaultMediaPlayer` creates a list of initial `codeph PlacementInformations` based on the ad signaling mode and ad metadata to be resolved by the `codeph MediaPlayerClient`.
  
  
* New ad signaling mode: Custom time ranges
  Ads are placed based on Time Range data from an external source (such as a JSON file).
  
  

