---
description: You can enable fallback when a VMAP inline ad contains an invalid media type.
seo-description: You can enable fallback when a VMAP inline ad contains an invalid media type.
seo-title: Define fallback ad behavior for VMAP inline ads
title: Define fallback ad behavior for VMAP inline ads
uuid: 2da78fe1-184d-469a-a96b-d20144ce4a63
index: y
internal: n
snippet: y
translate: y
---

# Define fallback ad behavior for VMAP inline ads

You can enable fallback when a VMAP inline ad contains an invalid media type.


1. Set `setFallbackOnInvalidCreativeEnabled` to `true` to have VMAP fall back when the media type for a linear/inline ad is invalid for HLS.

   The default value is `false`. If a linear ad fails because it is has an invalid media type, or because the ad cannot be repackaged, this flag allows Primetime ad decisioningto follow the same fallback behavior as if the ad was an empty VAST wrapper. 
   ```
   java   AuditudeSettings result = new AuditudeSettings(); 
   result.setFallbackOnInvalidCreative(true);
   ```

