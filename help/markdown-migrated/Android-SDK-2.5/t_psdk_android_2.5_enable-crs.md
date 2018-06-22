---
description: 
keywords: Enable CRS;Enable creative repackaging service
seo-description: 
seo-title: Enable CRS in TVSDK applications
title: Enable CRS in TVSDK applications
---

# Enable CRS in TVSDK applications

To enable CRS in your  applications, you must set the following information in your Auditude settings:

>1. Enable CRS in `codeph  AuditudeSettings`.
>   ```
>   ... 
>   auditudeSettings.setCreativeRepackagingEnabled(true); 
>   auditudeSettings.setCreativeRepackagingFormat("application/x-mpegURL");
>   ```
>   
>   
>   
