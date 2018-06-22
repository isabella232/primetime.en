---
description: These changes in the Android API support ad deletion and replacement.
seo-description: These changes in the Android API support ad deletion and replacement.
seo-title: Ad deletion and replacement API changes
title: Ad deletion and replacement API changes
---

# Ad deletion and replacement API changes

* `codeph AdSignalingMode`
  New Custom Time Range Ad Signaling Mode
  
  
* `codeph AdvertisingMetadata`
  New `codeph setTimeRanges(TimeRangeCollection timeRanges, Metadata options)`: Sets the time ranges to mark, delete, or replace when processing metadata
  
  
* `codeph ContentResolver`
    * New `codeph public final boolean canResolve(PlacementOpportunity placementOpportunity)`
    * New `codeph protected abstract boolean doCanResolve(PlacementOpportunity placementOpportunity)`
  
* New `codeph ContentRemoval` class
  `codeph TimelineOperation` class that defines the time range to be removed from the timeline
  
  
* `codeph AuditudeResolver`
    * New `codeph private LinkedList&lt;AuditudeRequest&gt; _requestQueue`
    * New `codeph void startConsumer()`: Starts processing the  request queue and ensures that each request is issued at `codeph MIN_INIT_REQUEST_INTERVAL` intervals
    * New `codeph processReplacementRange()`: Extracts time-ranges from the ad metadata and generates `codeph PlacementInformations`, and creates a  request containing the `codeph PlacementInformations`.
    * New `codeph canDoResolver()`: Checks if placement opportunity has  metadata
  
* New `codeph CustomRangeHelper`
  Helper class that extracts time range metadata from ad metadata, and removes subsets/overlaps/invalid time ranges.
  
  
* New `codeph DeleteContentResolver`
  Content resolver that resolves Placement opportunities of `codeph PlacementInformation.Mode.DELETE`
  
  
* New `codeph NopTimelineOperation`
  New timeline operation for when no ad break placement or replacement needs to be done. This class is used to distinguish between this and when an error occurs during the resolving process.
  
  
* `codeph TimelineOperationQueue`
  Checks if the Timeline Operation is a `codeph NopTimelineOperation` before processing.
  
  
* `codeph CustomAdMarkersContentResolver`
  New `codeph canDoResolve()`: Checks if a placement opportunity is of type `codeph Mode.MARK`
  
  
* `codeph MetadataResolver`
  New `codeph canDoResolve()`: Checks if a placement opportunity is of type `codeph Mode.INSERT`
  
  
* `codeph DefaultMetadataKeys`
  New `codeph TIME_RANGES_METADATA_KEY("time_ranges_metadata_key")`
  
  
* `codeph PlacementInformation`
    * New Mode `codeph enum (INSERT, DELETE, REPLACE, MARK)`
    * New Type `codeph CUSTOM_TIME_RANGES`
  
* `codeph TimeRange`
  New `codeph compareTo(TimeRange timeRange)`: So can sort TimeRanges based on begin time
  
  
* New `codeph ReplacementTimeRange`
  Extends the `codeph TimeRange` class that represents a replacement timerange, with a `codeph begin`, `codeph end`, and `codeph replacement-duration` parameter.
  
  
* `codeph TimeRangeCollection`
    * New `codeph MARK_RANGES, DELETE_RANGES, REPLACE_RANGES`
    * Renamed `codeph CUSTOM_AD_MARKERS` to `codeph MARK_RANGES`
    * Modified `codeph toMetadata(Metadata options)` to put delete/mark/replace ranges into ad metadata.
  
* `codeph MediaPlayerNotification`
    * New `codeph UNDEFINED_TIME_RANGES`: When the ad signaling mode is Server Map or Manifest Cues, and replace ranges are also in the ad metadata, replace ranges are ignored.
    * New `codeph REPLACE_RANGES_NOT_AVAILABLE`: When ad signaling mode is Custom Time Ranges and replace ranges are not available, a warning will be dispatched.
  
* `codeph AdvertisingFactory`
  New `codeph public abstract List&lt;ContentResolver&gt; createContentResolvers(MediaPlayerItem item)`
  
  
* `codeph DefaultAdvertisingFactory`
  New `codeph public List&lt;ContentResolver&gt; createContentResolvers(MediaPlayerItem item)`
  
  
* `codeph DefaultContentResolverFactory`
  New `codeph public static List&lt;ContentResolver&gt; createContentResolvers(MediaResource resource, Context context)`
  
  
* `codeph DefaultMediaPlayer`
    * In `codeph prepareToPlay()`: Makes an initial seek to 0, because if range `codeph [0,n]` is deleted, the media player will not automatically play.
    * In `codeph prepareToPlay()`: Loops through the list of initial placement informations for `codeph mediaplayerclient` to resolve.
    * In `codeph extractAdSignalingMode()`: Accommodate for the new Custom Time Range mode.
    * New `codeph private static List&lt;PlacementInformation&gt; createInitalPlacementInformations()`: Generates the initial placement informations for the ad signaling mode and content resolvers (derived from ad metadata).
    * In `codeph ContentPlacementCompletedListener`: Checks to see if `codeph mediaPlayerClient` is `codeph doneInitialResolving` before calling `codeph endAdResolving`.
  
* `codeph MediaPlayerClient`
    * New `codeph List&lt;ContentResolver&gt; _contentResolvers`
    * New `codeph int _reservations`
    * New `codeph lookupContentResolver(PlacementOpportunity placementOpportunity)`: Looks up which resolver can resolve the `codeph PlacementOpportunity`.
    * Modified code to create multiple content resolvers.
    * New `codeph public boolean doneInitialResolving()`: Checks if there are any opportunities left to be resolved.
  
* `codeph VideoEngineTimeline`
    * New `codeph removeContent(TimelineOperation timelineOperation)`: Removes a given range of content from timeline.
    * New `codeph removeContentByLocalTime(long begin, long end)`: Removes content by local time given `codeph begin` and `codeph end`.
  
* `codeph DefaultOpportunityDetectorFactory`
  Modified `codeph createOpportunityDetector`: For VOD streams, only return a new `codeph SpliceOutOpportunityDetector` if there are no MARK or REPLACE ranges (as those ranges have priority over the signaling mode).
  
  
