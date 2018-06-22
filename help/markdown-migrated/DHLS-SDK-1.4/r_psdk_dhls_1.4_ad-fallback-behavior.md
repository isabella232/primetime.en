---
---

<a id="section_9F60AF00CE9645848EAAF8C06A9E426B"></a>

In , the only valid media types are `codeph application/x-shockwave-flash` (VPAID) and `codeph application/x-mpegURL` (m3u8).

When there are stand-alone fallback ads, the  plug-in looks examines these ads in the following order and returns the first ad with a valid media type:
1. If repackaging is enabled, the first occurrence of an ad with an invalid media type is treated like other invalid media types.
   If repackaging fails, this process applies to additional occurrences of the ad.
   
   
1. If  finds no valid fallback ads, it returns the original ad with the invalid media type.
1. If a fallback ad with a valid MIME type is returned instead of the original ad,  sends error code 403 to the VAST error URL, if available.
1. If a fallback ad is a wrapper and returns multiple ads, only ads with the correct media type are returned.
>[!IMPORTANT]
>
>This behavior is always enabled for ads in VAST wrappers. For VAST ads inline in a VMAP, the behavior is disabled by default, but your application can enable it.

