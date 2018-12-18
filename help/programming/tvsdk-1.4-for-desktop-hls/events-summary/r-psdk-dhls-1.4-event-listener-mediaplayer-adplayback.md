---
description: TVSDK dispatches ad-playback events in response to ad-related operations such as when an ad starts playing.
seo-description: TVSDK dispatches ad-playback events in response to ad-related operations such as when an ad starts playing.
seo-title: Ad playback events
title: Ad playback events
uuid: 63138237-2315-45ff-914d-369da18fdff7
index: y
internal: n
snippet: y
---

# Ad playback events{#ad-playback-events}

TVSDK dispatches ad-playback events in response to ad-related operations such as when an ad starts playing.

 To be notified about all ad-playback related events, register listeners with the `MediaPlayer` object for the following events. 

>[!TIP]
>
>When ads are inserted into or removed from the media, TVSDK dispatches the playback event `TimelineEvent. [TIMELINE_UPDATED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimelineEvent.html#TIMELINE_UPDATED)`.

|  Event  | Meaning  |
|---|---|
| `AdBreakPlaybackEvent. [AD_BREAK_COMPLETED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_COMPLETED)`  | An ad break has played completely.  |
| `AdBreakPlaybackEvent. [AD_BREAK_SKIPPED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_SKIPPED)`  | An ad break was skipped during playback.  |
| `AdBreakPlaybackEvent. [AD_BREAK_STARTED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_STARTED)`  | An ad break has started.  |
| `AdClickEvent. [AD _CLICK](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdClickEvent.html#AD_CLICK)`  |The user has clicked the ad. Provides information to your application about the ad that the user clicked, in response to your application calling `notifyClick` on the `MediaPlayerView`.  |
| `AdPlaybackEvent. [AD _COMPLETED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_COMPLETED)`  | An ad has played completely.  |
| `AdPlaybackEvent. [AD _PROGRESS](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_PROGRESS)`  | Ad playback has progressed. Dispatched multiple times while an ad plays.  |
| `AdPlaybackEvent. [AD _SEEK](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_STARTED)`  | A seek has occurred across ad boundaries or within an ad.  |
| `AdPlaybackEvent. [AD _STARTED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_STARTED)`  | An ad has started.  |

