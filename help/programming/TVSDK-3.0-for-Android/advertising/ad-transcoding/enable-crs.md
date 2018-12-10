---
seo-title: Enable CRS in TVSDK applications
title: Enable CRS in TVSDK applications
uuid: fd9e625b-59c8-42c4-a207-2e91c352b6aa
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

