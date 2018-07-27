---
description: For Digital Video Ad Serving Template (VAST) ads (or creatives) that have the fallback rule enabled, treats an ad with an invalid media type as an empty ad and attempts to use fallback ads in its place. You can configure some aspects of fallback behavior.
seo-description: For Digital Video Ad Serving Template (VAST) ads (or creatives) that have the fallback rule enabled, treats an ad with an invalid media type as an empty ad and attempts to use fallback ads in its place. You can configure some aspects of fallback behavior.
seo-title: Ad fallback for VAST and VMAP ads
title: Ad fallback for VAST and VMAP ads
uuid: 065956be-6d9b-44ac-a213-77d3fc2b3cb9
index: n
internal: n
snippet: y
translate: y
---

# Ad fallback for VAST and VMAP ads

The VAST/Digital Video Multiple Ad Playlist (VMAP) specification states that for ads where VAST fallback is enabled, empty ads automatically trigger the use of fallback ads. When a VAST ad is empty,  <!-- PH element: phrases/primetime-sdk-name --> looks for a valid HLS media type replacement among the fallback ads. When a VAST ad in a wrapper has an invalid media type, <!-- PH element: phrases/primetime-sdk-name --> treats this ad as empty. You can configure whether <!-- PH element: phrases/primetime-sdk-name --> should do the same for ads inline in a VMAP. For more information about the VAST `fallbackOnNoAd` feature, see [Digital Video Ad Serving Template (VAST) 3.0](http://www.iab.net/guidelines/508676/digitalvideo/vsuite/vast). 
