---
description: You can enable fallback when a VMAP inline ad contains an invalid media type.
seo-description: You can enable fallback when a VMAP inline ad contains an invalid media type.
seo-title: Define fallback ad behavior for VMAP inline ads
title: Define fallback ad behavior for VMAP inline ads
uuid: 758d2a84-1d44-493e-b57f-324a4c7ea407
index: n
internal: n
snippet: y
translate: y
---

# Define fallback ad behavior for VMAP inline ads


>1. Set ` setFallbackOnInvalidCreativeEnabled` to ` true` to have VMAP fall back when the media type for a linear/inline ad is invalid for HLS.
>   The default value is ` false`. If a linear ad fails because it is has an invalid media type, or because the ad cannot be repackaged, this flag allows  <!-- PH element: phrases/auditude-name --> to follow the same fallback behavior as if the ad was an empty VAST wrapper.>
>   ```
>   java>   AuditudeSettings result = new AuditudeSettings(); 
>   result.setFallbackOnInvalidCreative(true);
>   ```
>
