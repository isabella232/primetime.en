---
description: You can enable fallback when a VMAP inline ad contains an invalid media type.
seo-description: You can enable fallback when a VMAP inline ad contains an invalid media type.
seo-title: Define fallback ad behavior for VMAP inline ads
title: Define fallback ad behavior for VMAP inline ads
uuid: 5d998e4a-9550-4f22-b3d1-e4177b627c8a
index: y
internal: n
snippet: y
---

# Define fallback ad behavior for VMAP inline ads{#define-fallback-ad-behavior-for-vmap-inline-ads}

You can enable fallback when a VMAP inline ad contains an invalid media type.

1. Set `setFallbackOnInvalidCreativeEnabled` to `true` to have VMAP fall back when the media type for a linear/inline ad is invalid for HLS.

   The default value is `false`. If a linear ad fails because it is has an invalid media type, or because the ad cannot be repackaged, this flag allows Primetime ad decisioningto follow the same fallback behavior as if the ad was an empty VAST wrapper. 

   ```java
   AuditudeSettings result = new AuditudeSettings(); 
   result.setFallbackOnInvalidCreative(true);
   ```
