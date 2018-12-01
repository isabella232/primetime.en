---
description: null
keywords: Enable CRS;Enable creative repackaging service
seo-description: null
seo-title: Enable CRS in TVSDK applications
title: Enable CRS in TVSDK applications
uuid: 965c12bb-d932-4305-8eb1-2cdd64d36d60
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

