---
description: Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. and can optionally attempt to repackage incompatible ads into compatible M3U8 videos.
seo-description: Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. and can optionally attempt to repackage incompatible ads into compatible M3U8 videos.
seo-title: Repackage incompatible ads using Adobe Creative Repackaging Service (CRS)
title: Repackage incompatible ads using Adobe Creative Repackaging Service (CRS)
uuid: 188d6e2f-5183-46b0-9a63-535188f7eb63
index: n
internal: n
snippet: y
translate: y
---

# Repackage incompatible ads using Adobe Creative Repackaging Service (CRS)

Ads served from various third parties, such as an agency ad server, your inventory partner, or an ad network, are often delivered in incompatible formats, such as the progressive download MP4 format.
When  <!-- PH element: phrases/primetime-sdk-name --> first encounters an incompatible ad, the player ignores the ad and issues a request to the <!-- PH element: phrases/crs-name --> ( <!-- PH element: phrases/crs-acronym --> ), which is part of the <!-- PH element: phrases/ad-insert-name --> back end, to repackage the ad into a compatible format. <!-- PH element: phrases/crs-acronym --> attempts to generate multiple bit rate M3U8 renditions of the ad and stores these renditions on the Primetime Content Delivery Network (CDN). The next time <!-- PH element: phrases/primetime-sdk-name --> receives an ad response that points to that ad, the player uses the HLS-compatible M3U8 version from the CDN.
To activate this optional CRS feature, contact your Adobe representative. 
>[!NOTE]
>
>For <!-- PH element: phrases/crs-acronym --> Version 3.0 (and earlier) customers, beginning with <!-- PH element: phrases/crs-acronym --> Version 3.1 the following changes have improved both security and performance:>
>* <!-- PH element: phrases/crs-acronym --> 3.1 continues with `https:` if the content being repackaged uses `https:`. This reduces the potential for some players to present unsecure content.
>* <!-- PH element: phrases/crs-acronym --> 3.1 greatly minimizes network calls, improving video startup time.



For more information about CRS, see [Creative Packaging Service (CRS)](http://help.adobe.com/en_US/primetime/crs/index.html). 
