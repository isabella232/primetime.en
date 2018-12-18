---
description: null
keywords: Enable CRS;Enable creative repackaging service
seo-description: null
seo-title: Enable CRS in TVSDK applications
title: Enable CRS in TVSDK applications
uuid: 2243988f-505c-4998-bc0b-d48a166ca429
index: y
internal: n
snippet: y
---

# Enable CRS in TVSDK applications{#enable-crs-in-tvsdk-applications}

To enable CRS in your TVSDK applications, you must set the following information in your Auditude settings:

1. Enable CRS in `AuditudeSettings`.

   ```
   ... 
   auditudeSettings.setCreativeRepackagingEnabled(true); 
   auditudeSettings.setCreativeRepackagingFormat("application/x-mpegURL"); 
   ```

