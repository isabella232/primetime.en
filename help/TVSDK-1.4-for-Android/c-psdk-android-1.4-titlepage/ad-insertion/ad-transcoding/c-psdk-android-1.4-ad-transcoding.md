---
description: Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. Primetime ad insertion and TVSDK can optionally attempt to repackage incompatible ads into compatible M3U8 videos.
seo-description: Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. Primetime ad insertion and TVSDK can optionally attempt to repackage incompatible ads into compatible M3U8 videos.
seo-title: Repackage incompatible ads using Adobe Creative Repackaging Service
title: Repackage incompatible ads using Adobe Creative Repackaging Service
uuid: c026eddc-f03e-48bf-be14-6e1b1c336117
index: y
internal: n
snippet: y
---

# Repackage incompatible ads using Adobe Creative Repackaging Service{#repackage-incompatible-ads-using-adobe-creative-repackaging-service}

Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. Primetime ad insertion and TVSDK can optionally attempt to repackage incompatible ads into compatible M3U8 videos.

Ads served from various third parties, such as an agency ad server, your inventory partner, or an ad network, are often delivered in incompatible formats, such as progressive-download MP4.

When TVSDK first encounters an incompatible ad, the player ignores the ad and issues a request to the creative repackaging service (CRS), which is part of the Primetime ad insertion back end, to repackage the ad into a compatible format. CRS attempts to generate multiple-bit-rate M3U8 renditions of the ad and stores these renditions on the Primetime Content Delivery Network (CDN). The next time TVSDK receives an ad response that points to that ad, the player uses the HLS-compatible M3U8 version from the CDN.

To enable this optional feature, contact your Adobe representative.

For more information about CRS, see [Creative Packaging Service (CRS)](http://help.adobe.com/en_US/primetime/crs/index.html). 
