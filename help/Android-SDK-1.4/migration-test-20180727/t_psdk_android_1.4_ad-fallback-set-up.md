---
description: You can turn on fallback when a VMAP inline ad contains an invalid media type.
seo-description: You can turn on fallback when a VMAP inline ad contains an invalid media type.
seo-title: Define fallback ad behavior for VMAP inline ads
title: Define fallback ad behavior for VMAP inline ads
uuid: d1223ab3-e72d-4489-b7c2-1976f9237c2f
index: n
internal: n
snippet: y
translate: y
---

# Define fallback ad behavior for VMAP inline ads


>1. Set ` setFallbackOnInvalidCreativeEnabled` to ` true` to have VMAP fall back when the media type for a linear/inline ad is invalid for HLS.
>   The default value is false. If a linear ad fails because it is has an invalid media type, or because the ad cannot be repackaged, this flag allows <!-- PH element: phrases/auditude-name --> to follow the same fallback behavior as if the ad was an empty VAST wrapper.>

>    
>       ```
>       java>       AuditudeSettings result = new AuditudeSettings(); 
>       result.setFallbackOnInvalidCreative(true);
>       ```
