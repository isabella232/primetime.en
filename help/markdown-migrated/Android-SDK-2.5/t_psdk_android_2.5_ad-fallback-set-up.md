---
description: You can enable fallback when a VMAP inline ad contains an invalid media type.
seo-description: You can enable fallback when a VMAP inline ad contains an invalid media type.
seo-title: Define fallback ad behavior for VMAP inline ads
title: Define fallback ad behavior for VMAP inline ads
---

# Define fallback ad behavior for VMAP inline ads

>1. Set `codeph  setFallbackOnInvalidCreativeEnabled` to `codeph  true` to have VMAP fall back when the media type for a linear/inline ad is invalid for HLS.
>   The default value is`codeph  false`. If a linear ad fails because it is has an invalid media type, or because the ad cannot be repackaged, this flag allows  to follow the same fallback behavior as if the ad was an empty VAST wrapper.
>   ```java
>   AuditudeSettings result = new AuditudeSettings(); 
>   result.setFallbackOnInvalidCreative(true);
>   ```
>   
>   
>   
