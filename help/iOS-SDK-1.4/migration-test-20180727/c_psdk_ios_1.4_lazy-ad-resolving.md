---
description: Ad resolving and ad loading can cause a delay as you wait for playback to start. Lazy ad loading and lazy ad resolving can reduce this startup delay.
keywords: Lazy;Ad resolving;Ad loading
seo-description: Ad resolving and ad loading can cause a delay as you wait for playback to start. Lazy ad loading and lazy ad resolving can reduce this startup delay.
seo-title: Lazy ad resolving
title: Lazy ad resolving
uuid: ef5e1525-cbb9-44fa-b65c-9e1ef8db2c57
index: n
internal: n
snippet: y
translate: y
---

# Lazy ad resolving

The basic process of ad resolving is composed of these steps:

1. <!-- PH element: phrases/primetime-sdk-name --> downloads the manifest (playlist).
1. <!-- PH element: phrases/primetime-sdk-name --> resolves all of the ads.
1. <!-- PH element: phrases/primetime-sdk-name --> loads all of the ads and places them on the timeline.
1. <!-- PH element: phrases/primetime-sdk-name --> moves the player into the READY state, and content playback begins.
The player uses the URLs in the manifest to obtain the ad content (creatives), ensures that the ad content is in a format that  <!-- PH element: phrases/primetime-sdk-name --> can play, and <!-- PH element: phrases/primetime-sdk-name --> places the ads on the timeline. This basic process of resolving and loading ads can cause a long delay in playing content, especially if the manifest contains several ad creatives.
Lazy ad resolving allows for a faster start-up by resolving only pre-roll ads before start-up. The process of lazy ad resolving is composed of these steps:

1. <!-- PH element: phrases/primetime-sdk-name --> downloads the playlist.
1. <!-- PH element: phrases/primetime-sdk-name --> resolves and loads only the pre-roll ads, moves the player into the READY state, and content playback begins.
1. <!-- PH element: phrases/primetime-sdk-name --> resolves and loads the remaining ads and places them on the timeline as playback occurs at or before the expected time of an ad break.

>[!IMPORTANT]
>
>Consider these factors when you work with lazy ad resolving:
>
>* Lazy ad resolving is disabled by default on iOS. If you keep lazy ad resolving disabled, all ads are resolved before playback starts.
>* Lazy ad resolving is for VOD only. It will not work with LIVE streams.
>* Lazy ad resolution does not affect pre-roll ads.
>* If the code allows the pre-roll and the mid-roll ad to play, then, at 30 seconds, just before the mid-roll ad plays, there is a black screen for two seconds. The source of this behavior is the dual-player approach which has a drawback in the visible delay in the transition between>
>    * content and an ad break
>    * one ad and another ad
>  <!-- This has to do with https://jira.corp.adobe.com/browse/PTPLAY-19279. I'm leaving it in although the placement is probably erroneous with respect to lazy ad loading. A search for mid-roll might reveal a better place or at least another place. -->


