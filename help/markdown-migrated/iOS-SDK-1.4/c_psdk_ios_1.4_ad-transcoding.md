---
description: Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. and can optionally attempt to repackage incompatible ads into compatible M3U8 videos.
seo-description: Some third-party ads (or creatives) cannot be stitched into the HTTP Live Streaming (HLS) content stream because their video format is incompatible with HLS. and can optionally attempt to repackage incompatible ads into compatible M3U8 videos.
seo-title: Repackage incompatible ads using Adobe Creative Repackaging
	 Service
title: Repackage incompatible ads using Adobe Creative Repackaging
	 Service
---

# Repackage incompatible ads using Adobe Creative Repackaging
	 Service

Ads served from various third parties, such as an agency ad server, your inventory partner, or an ad network, are often delivered in incompatible formats, such as progressive-download MP4.

When  first encounters an incompatible ad, the player ignores the ad and issues a request to the  (), which is part of the  back end, to repackage the ad into a compatible format.  attempts to generate multiple-bit-rate M3U8 renditions of the ad and stores these renditions on the Primetime Content Delivery Network (CDN). The next time  receives an ad response that points to that ad, the player uses the HLS-compatible M3U8 version from the CDN.

To enable this optional feature, contact your Adobe representative.

For more information about CRS, see [Creative Packaging Service (CRS)](http://help.adobe.com/en_US/primetime/crs/index.html).

