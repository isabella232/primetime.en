---
description: null
keywords: Enable CRS;Enable creative repackaging service
seo-description: null
seo-title: Enable CRS in TVSDK applications
title: Enable CRS in TVSDK applications
uuid: 2d38de37-c19e-4f96-9861-e5c6b3d1b3ef
index: y
internal: n
snippet: y
translate: y
---

# Enable CRS in TVSDK applications

To enable CRS in your TVSDK applications, you must set the following information in your Auditude settings:

1. Enable CRS in `AuditudeSettings`.

   ```
   ... 
   auditudeSettings.setCreativeRepackagingEnabled(true); 
   auditudeSettings.setCreativeRepackagingFormat("application/x-mpegURL"); 
   ```

