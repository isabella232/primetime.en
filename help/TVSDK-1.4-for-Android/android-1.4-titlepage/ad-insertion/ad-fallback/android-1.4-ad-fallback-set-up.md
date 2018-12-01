---
description: You can turn on fallback when a VMAP inline ad contains an invalid media type.
seo-description: You can turn on fallback when a VMAP inline ad contains an invalid media type.
seo-title: Define fallback ad behavior for VMAP inline ads
title: Define fallback ad behavior for VMAP inline ads
uuid: c9c209a7-bbf3-461d-b0a8-e21e03de9e23
index: y
internal: n
snippet: y
---

# Define fallback ad behavior for VMAP inline ads{#define-fallback-ad-behavior-for-vmap-inline-ads}

You can turn on fallback when a VMAP inline ad contains an invalid media type.

1. Set `setFallbackOnInvalidCreativeEnabled` to `true` to have VMAP fall back when the media type for a linear/inline ad is invalid for HLS.

   The default value is false. If a linear ad fails because it is has an invalid media type, or because the ad cannot be repackaged, this flag allows Primetime ad decisioning to follow the same fallback behavior as if the ad was an empty VAST wrapper.

   ```java
   AuditudeSettings result = new AuditudeSettings(); 
   result.setFallbackOnInvalidCreative(true);
   ```

