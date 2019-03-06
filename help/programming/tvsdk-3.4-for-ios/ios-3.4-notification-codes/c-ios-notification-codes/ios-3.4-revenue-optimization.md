---
description: This table provides detailed information about INFO type notifications.
seo-description: This table provides detailed information about INFO type notifications.
seo-title: INFO notification codes
title: INFO notification codes
uuid: 21297863-dac1-45a4-ac9d-309d1f746f8b
---

# REVENUE Optimization code {#revenue-optimization-code}

This table provides detailed information about REVENUE OPTIMIZATION notifications.

## Enable Revenue Optimization Reporting {enable-revenue-optimization-reporting}

To enable this reporting, use PTMediaPlayer api: `[mediaPlayer
setRevenueOptimizationReportingLevel:PTNotificationTypeInfo]`.

[!Note]: Most informational notifications contain relevant metadata, for example, the URL of the resource that failed to download. Some notifications contain metadata to specify whether the problem occurred in the main video content, in the alternate audio content, or in an ad.

<table frame="all" colsep="1" rowsep="1" id="table_503463046E764A87B10EB5D8B294EB23"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"><b>Code</b></th> 
   <th colname="2" class="entry"><b>Name</b></th> 
   <th colname="3" class="entry"><b>Inner Notification</b></th> 
   <th colname="4" class="entry"><b>Metadata Keys</b></th> 
   <th colname="5" class="entry"><b>Comments</b></th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"><span class="codeph"> 400101 </span> </td> 
   <td colname="2"><span class="codeph"> REVENUE_OPTIMIZATION_REPORTING </span> </td> 
   <td colname="3"> None </td> 
   <td colname="4"> Refer below table for metadata keys based on different events. </td> 
   <td colname="5"> None </td> 
  </tr> 
 </tbody> 
</table>
<table frame="all" colsep="1" rowsep="1">
<thead>
<tr rowsep="1"> 
   <th colname="1" class="entry"><b>Event Details</b></th> 
   <th colname="2" class="entry"><b>ContextMetadata</b></th> 
</tr> 
 </thead>
 <tbody> 
<tr rowsep="1"> 
   <td colname="1"><span class="codeph"><b>CONTENT_RESOURCE_START</b>
   Dispatched in TVSDK when MediaPlayer::replaceCurrentResource is called.
   </span> </td> 
   <td colname="2"><span class="codeph"> clientTimestamp, fallbackOnInvalidCreative, showStaticBanners, hasPreroll, event, adSignalingMode, resourceUrl, creativeRepackagingFormat, delayAdLoadingTolerance, zoneID, hasLivePreroll, adRequestTimeout, delayAdLoading, resourceType, creativeRepackagingEnabled, mediaId, clientId </span> </td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>CONTENT_PLAYBACK_START</b>
   Dispatched in TVSDK when content has entered the prepared state and is ready for playback.

   This event will not dispatch on every manifest upload - will only dispatch on the initial load. </span> </td> 
   <td colname="2"><span class="codeph"> clientTimestamp, contentURL, contentType, event, isLive, clientID </span> </td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_OPPORTUNITY_GENERATED</b>
   Dispatched in TVSDK when an opportunity is generated.
   </span> </td>
<td colname="2"><span class="codeph"> clientTimestamp, event, opportunityId, placementDuration, clientId </span> </td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_OPPORTUNITY_RESOLVE_START</b>
   Dispatched in TVSDK when an opportunity begins resolving.
   </span> </td>
<td colname="2"><span class="codeph">clientTimestamp, event, opportunityId, placementDuration, clientId </span> </td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_OPPORTUNITY_RESOLVE_FAILED</b>
   Dispatched in TVSDK when an ad resolver calls MediaPlayerClient::notifyFailed().

   Need to fill in data
   </span> </td>
<td colname="2"><span class="codeph">opportunityId, notificationAD </span> </td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_RESOURCE_LOAD</b> 

Dispatched when any ad resource is fetched by URL.

responseStartTime:Unix timestamp for when the request first started.

responseTotalTime:Total amount of time (in seconds) that it took for a response to load.

responseStatus:The status code encountered while fetching the resource 

status:"error" or "success"

referrerAdId:The referring ad id that requested fetching of this resource (if present)

referrerUrl:The referring url that requested fetching of this resource

errorMessage:If the status is "error", the reason for the error will be located here.
   </span> </td>
<td colname="2"><span class="codeph">opportunityId, resourceType, responseTotalTime, responseStatus,
responseStartTime, status, errorMessage, url, referrerURL, referrerAdId </span> </td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_RESOURCE_LOAD_CRS</b> 

Dispatched in TVSDK when a CRS is applied to an asset, as well as the response for the m3u8.

resourceType:always "crs"

responseStartTime:Unix timestamp for when the request first started.

responseTotalTime:Total amount of time (in seconds) that it took for a response to load

responseStatus:The status code encountered while fetching the resource

status:"error" or "success"

errorMessage:If the status is "error", the reason for the error will be located here.

mediaFileUrl:The original media file url that was selected

mediaFileBitrate:The bitrate of the media file that was selected

mediaFileMimeType: The mime type of the media file that was selected

url:The final asset ur
   </span> </td>
<td colname="2"><span class="codeph">opportunityId, resourceType, responseTotalTime, responseStatus,
responseStartTime, status, errorMessage, url, mediaFileURL, mediaFileBitrate, mediaFileMimeType, url</span> </td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_TIMELINE_PLACE</b> 

Dispatched in TVSDK after an adBreak was placed on the timeline. This event will occur once for each ad break.

proposedTime:The time in which the ad break was requested to be placed

actualTime:The time in which the ad break was actually placed

proposedDuration:The duration of the ad break that was requested for insertion. For live content this would be
the cue duration. For VOD content this would normally be -1.

actualDuration:The actual duration of the ad break inserted. Calculated as the sum duration of all ads, defined by their
respective segment durations, added or replaced in the original stream timeline.

proposedAds:The number of ads in the proposed ad break.

totalAds:The number of ads that were successfully placed.

ads...n:The successfully insert ads will be inserted here. Entire ad manifest information can be retrieved from
AD_OPPORTUNITY_RESOLVE_PROCESS
   </span> </td>
<td colname="2"><span class="codeph">opportunityId, status, errorMessage, proposedTime, proposedDuration, actualTime, actualDuration, proposedAds, totalAds, ads_id, ads_type,
ads_duration, ads_url</span> </td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_PLAYBACK_START</b>

Dispatched in TVSDK after an ad begins playback.</span> </td>
<td colname="2"><span class="codeph">clientTimestamp, event, id, url, duration, type, opportunityId, clientId</span></td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_PLAYBACK_COMPLETE</b>

Dispatched in TVSDK after an ad completes playback. </span> </td>
<td colname="2"><span class="codeph">clientTimestamp, event, id, url, duration, type, opportunityId, clientId</span></td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>ADBREAK_PLAYBACK_START</b>

Dispatched in TVSDK when an adbreak starts playback. </span> </td>
<td colname="2"><span class="codeph">clientTimestamp, event, id, opportunityId, duration, time, clientId</span></td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>ADBREAK_PLAYBACK_COMPLETE</b>

Dispatched in TVSDK when an adbreak completes playback. </span> </td>
<td colname="2"><span class="codeph">clientTimestamp, event, opportunityId, clientId</span></td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>CONTENT_PLAYBACK_COMPLETE</b>

Dispatched in TVSDK when any content is completed.This could occur if the stream is replaced, the player enters an error state, the player is reset, or the content actually completes. This event will be necessary to track a sessionId </span> </td>
<td colname="2"><span class="codeph">clientTimestamp, event, clientId, url, status, errorMessage</span></td>
<tr rowsep="1"> 
<td colname="1"><span class="codeph"><b>AD_PLAYBACK_ERROR</b>

Dispatched in TVSDK when an ad has an error playing back (variant stream errors). </span> </td>
<td colname="2"><span class="codeph">event, error, Timestamp, manifestUrl, time, opportunityId, url</span></td>