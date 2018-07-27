---
description: Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. and can optionally attempt to repackage incompatible ads into compatible M3U8 videos.
seo-description: Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. and can optionally attempt to repackage incompatible ads into compatible M3U8 videos.
seo-title: Repackage incompatible ads using Adobe Creative Repackaging Service
title: Repackage incompatible ads using Adobe Creative Repackaging Service
uuid: f17324e9-5159-4db2-a051-dff765726ece
index: n
internal: n
snippet: y
translate: y
---

# Repackage incompatible ads using Adobe Creative Repackaging Service

Ads served from various third parties, such as an agency ad server, your inventory partner, or an ad network, are often delivered in incompatible formats, such as progressive-download MP4.
When  <!-- PH element: phrases/primetime-sdk-name --> first encounters an incompatible ad, the player ignores the ad and issues a request to the <!-- PH element: phrases/crs-name --> ( <!-- PH element: phrases/crs-acronym --> ), which is part of the <!-- PH element: phrases/ad-insert-name --> back end, to repackage the ad into a compatible format. <!-- PH element: phrases/crs-acronym --> attempts to generate multiple-bit-rate M3U8 renditions of the ad and stores these renditions on the Primetime Content Delivery Network (CDN). The next time <!-- PH element: phrases/primetime-sdk-name --> receives an ad response that points to that ad, the player uses the HLS-compatible M3U8 version from the CDN.
To enable this optional feature, contact your Adobe representative.
For more information about CRS, see [Creative Packaging Service (CRS)](http://help.adobe.com/en_US/primetime/crs/index.html). 
