---
description: For Digital Video Ad Serving Template (VAST) ads (or creatives) that have the fallback rule enabled, treats an ad with an invalid media type as an empty ad and attempts to use fallback ads in its place. You can configure some aspects of fallback behavior.
keywords: zero length ad;empty ad
seo-description: For Digital Video Ad Serving Template (VAST) ads (or creatives) that have the fallback rule enabled, treats an ad with an invalid media type as an empty ad and attempts to use fallback ads in its place. You can configure some aspects of fallback behavior.
seo-title: Ad fallback for VAST and VMAP ads
title: Ad fallback for VAST and VMAP ads
uuid: 76cbddc7-6006-47ed-b186-aee1e244772a
index: n
internal: n
snippet: y
translate: y
---

# Ad fallback for VAST and VMAP ads

The VAST/Digital Video Multiple Ad Playlist (VMAP) specification states that for ads that have VAST fallback enabled, empty ads automatically trigger the use of fallback ads. When a VAST ad is empty,  <!-- PH element: phrases/primetime-sdk-name --> looks for a valid HLS media type replacement among the fallback ads. When a VAST ad in a wrapper has an invalid media type, <!-- PH element: phrases/primetime-sdk-name --> treats this ad as empty. You can configure whether <!-- PH element: phrases/primetime-sdk-name --> should do the same for ads inline in a VMAP. For more information about the VAST `fallbackOnNoAd` feature, see [Digital Video Ad Serving Template (VAST) 3.0](http://www.iab.net/guidelines/508676/digitalvideo/vsuite/vast). 

>[!NOTE]
>
>**Zero Length Ads** - When  <!-- PH element: phrases/primetime-sdk-name --> encounters a VAST response that contains an ad of zero duration, or an ad break with no ads, it fires AD_BREAK_START / AD_BREAK_COMPLETE events for those zero-length ad breaks.*This behavior applies only for VOD streams.* <!-- PH element: phrases/primetime-sdk-name --> fires these events even when your app is using the SKIP ad policy. <!-- PH element: phrases/primetime-sdk-name --> does*not* fire AD_BREAK_START / AD_BREAK_COMPLETE events for Live streams, or when a user employs trickplay or seek to go past the zero-length ad. 



