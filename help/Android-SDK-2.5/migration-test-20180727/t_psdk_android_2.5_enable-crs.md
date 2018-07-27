---
description: null
keywords: Enable CRS;Enable creative repackaging service
seo-description: null
seo-title: Enable CRS in TVSDK applications
title: Enable CRS in TVSDK applications
uuid: 1d66902f-8d2e-42cb-9969-9e11d27db35b
index: n
internal: n
snippet: y
translate: y
---

# Enable CRS in TVSDK applications

To enable CRS in your  <!-- PH element: phrases/primetime-sdk-name --> applications, you must set the following information in your Auditude settings:

>1. Enable CRS in ` AuditudeSettings`.
>
>   ```
>   ... 
>   auditudeSettings.setCreativeRepackagingEnabled(true); 
>   auditudeSettings.setCreativeRepackagingFormat("application/x-mpegURL"); 
>   ```
>
