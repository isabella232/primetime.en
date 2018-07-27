---
description: You can turn on fallback when a VMAP inline ad contains an invalid media type.
seo-description: You can turn on fallback when a VMAP inline ad contains an invalid media type.
seo-title: Define fallback ad behavior for VMAP inline ads
title: Define fallback ad behavior for VMAP inline ads
uuid: 14155f5b-ce46-4eef-8f21-d380d1a4e592
index: n
internal: n
snippet: y
translate: y
---

# Define fallback ad behavior for VMAP inline ads


>1. Set ` FallbackOnInvalidCreativeEnabled` to ` YES` to have VMAP fall back when the media type for a linear/inline ad is invalid for HLS.
>   The default value is NO. If a linear ad fails because it is has an invalid media type, or because the ad cannot be repackaged, this flag allows <!-- PH element: phrases/auditude-name --> to follow the same fallback behavior as if the ad was an empty VAST wrapper.>

>    
>       ```
>       PTAuditudeMetadata *adMetadata = [[[PTAuditudeMetadata alloc] init] autorelease]; 
>       adMetadata.isFallbackOnInvalidCreativeEnabled = YES;
>       ```
