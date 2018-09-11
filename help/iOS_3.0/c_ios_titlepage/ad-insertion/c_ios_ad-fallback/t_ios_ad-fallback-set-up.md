---
description: You can turn on fallback when a VMAP inline ad contains an invalid media type.
seo-description: You can turn on fallback when a VMAP inline ad contains an invalid media type.
seo-title: Define fallback ad behavior for VMAP inline ads
title: Define fallback ad behavior for VMAP inline ads
uuid: 5592ba3c-0abf-4cad-9f00-f3c5e005cca7
index: y
internal: n
snippet: y
translate: y
---

# Define fallback ad behavior for VMAP inline ads

You can turn on fallback when a VMAP inline ad contains an invalid media type.


1. Set `FallbackOnInvalidCreativeEnabled` to `YES` to have VMAP fall back when the media type for a linear/inline ad is invalid for HLS.

   The default value is NO. If a linear ad fails because it is has an invalid media type, or because the ad cannot be repackaged, this flag allows Primetime ad decisioning to follow the same fallback behavior as if the ad was an empty VAST wrapper.

   ```
   PTAuditudeMetadata *adMetadata = [[[PTAuditudeMetadata alloc] init] autorelease]; 
   adMetadata.isFallbackOnInvalidCreativeEnabled = YES;
   ```
