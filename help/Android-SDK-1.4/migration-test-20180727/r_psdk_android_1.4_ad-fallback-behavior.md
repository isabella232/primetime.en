---
description: When encounters a VAST ad (creative) that is empty or that has a media type that is invalid for HLS, it evaluates the fallback ads to determine what to return.
seo-description: When encounters a VAST ad (creative) that is empty or that has a media type that is invalid for HLS, it evaluates the fallback ads to determine what to return.
seo-title: Ad fallback behavior for VAST and VMAP
title: Ad fallback behavior for VAST and VMAP
uuid: cf609d33-cdfc-4e65-b365-faf45d32f3dd
index: n
internal: n
snippet: y
translate: y
---

# Ad fallback behavior for VAST and VMAP


<a id="section_9F60AF00CE9645848EAAF8C06A9E426B"></a>

In  <!-- PH element: phrases/primetime-sdk-name --> , the only valid media type is `application/x-mpegURL` (M3U8). 
When there are stand-alone fallback ads, the  <!-- PH element: phrases/auditude-name --> plug-in looks examines these ads in the following order and returns the first ad with a valid media type:
1. If repackaging is enabled, the first occurrence of an ad with an invalid media type is treated like other invalid media types. If repackaging fails, this process applies to additional occurrences of the ad.

1. If  <!-- PH element: phrases/primetime-sdk-name --> finds no valid fallback ads, it returns the original ad with the invalid media type.
1. If a fallback ad with a valid MIME type is returned instead of the original ad,  <!-- PH element: phrases/auditude-name --> sends error code 403 to the VAST error URL, if available.
1. If a fallback ad is a wrapper and returns multiple ads, only ads with the correct media type are returned.

>[!IMPORTANT]
>
>This behavior is always enabled for ads in VAST wrappers. For VAST ads inline in a VMAP, the behavior is disabled by default, but your application can enable it.


