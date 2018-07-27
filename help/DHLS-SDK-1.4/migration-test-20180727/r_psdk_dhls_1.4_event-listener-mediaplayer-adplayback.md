---
description: dispatches ad-playback events in response to ad-related operations such as when an ad starts playing.
seo-description: dispatches ad-playback events in response to ad-related operations such as when an ad starts playing.
seo-title: Ad playback events
title: Ad playback events
uuid: 336e0b2d-44d3-41f0-9498-3c8a9b686199
index: n
internal: n
snippet: y
translate: y
---

# Ad playback events


>`MediaPlayer`
>>[!TIP]
>>
>>When ads are inserted into or removed from the media, <!-- PH element: phrases/primetime-sdk-name --> dispatches the playback event `TimelineEvent.[TIMELINE_UPDATED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimelineEvent.html#TIMELINE_UPDATED)`. 
>

>| Event |Meaning |
>|---|---|
>| `AdBreakPlaybackEvent.[AD_BREAK_COMPLETED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_COMPLETED)` |An ad break has played completely. |
>| `AdBreakPlaybackEvent.[AD_BREAK_SKIPPED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_SKIPPED)` |An ad break was skipped during playback. |
>| `AdBreakPlaybackEvent.[AD_BREAK_STARTED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_STARTED)` |An ad break has started. |
>| `AdClickEvent.[AD _CLICK](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdClickEvent.html#AD_CLICK)` |The user has clicked the ad. Provides information to your application about the ad that the user clicked, in response to your application calling `notifyClick` on the `MediaPlayerView`.  |
>| `AdPlaybackEvent.[AD _COMPLETED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_COMPLETED)`  |An ad has played completely. |
>| `AdPlaybackEvent.[AD _PROGRESS](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_PROGRESS)`  |Ad playback has progressed. Dispatched multiple times while an ad plays. |
>| `AdPlaybackEvent.[AD _SEEK](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_STARTED)`  |A seek has occurred across ad boundaries or within an ad. |
>| `AdPlaybackEvent.[AD _STARTED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_STARTED)` |An ad has started. |

