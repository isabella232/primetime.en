---
description: TVSDK dispatches ad-playback events in response to ad-related operations such as when an ad starts playing.
seo-description: TVSDK dispatches ad-playback events in response to ad-related operations such as when an ad starts playing.
seo-title: Ad playback events
title: Ad playback events
uuid: 8b9de685-0ee8-4054-893b-80cd0cdd673c
index: y
internal: n
snippet: y
---

# Ad playback events{#ad-playback-events}

TVSDK dispatches ad-playback events in response to ad-related operations such as when an ad starts playing.

 To be notified about all ad-playback related events, register an implementation of `MediaPlayer.AdPlaybackEventListener` including the following callbacks. 

>[!TIP]
>
>When ads are inserted into or removed from the media, TVSDK dispatches the playback event [onTimelineUpdated](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onTimelineUpdated()).

|  Event  | Meaning  |
|---|---|
| ` [onAdBreakComplete](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdBreakComplete(com.adobe.mediacore.timeline.advertising.AdBreak)) (AdBreak adBreak)`  | An ad break has played completely.  |
| `onAdBreakSkipped`  | An ad break was skipped during playback.  |
| ` [onAdBreakStart](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdBreakStart(com.adobe.mediacore.timeline.advertising.AdBreak)) (AdBreak adBreak)`  | An ad break has started.  |
| ` [onAdClick](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdClick(com.adobe.mediacore.timeline.advertising.AdBreak,%20com.adobe.mediacore.timeline.advertising.Ad,%20com.adobe.mediacore.timeline.advertising.AdClick)) (AdBreak adBreak, Ad ad, AdClick adClick)`  |The user has clicked the ad. Provides information to your application about the ad that the user clicked, in response to your application calling `notifyClick` on the `MediaPlayerView`.  |
| ` [onAdComplete](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdComplete(com.adobe.mediacore.timeline.advertising.AdBreak)) (AdBreak adBreak, Ad ad)`  | An ad has played completely.  |
| ` [onAdProgress](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdProgress(com.adobe.mediacore.timeline.advertising.AdBreak,com.adobe.mediacore.timeline.advertising.Ad,%20int)) (AdBreak adBreak, Ad ad, int percentage)`  | Ad playback has progressed. Dispatched multiple times while an ad plays.  |
| ` [onAdStart](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdStart(com.adobe.mediacore.timeline.advertising.AdBreak,%20com.adobe.mediacore.timeline.advertising.Ad)) (AdBreak adBreak, Ad ad)`  | An ad has started.  |

