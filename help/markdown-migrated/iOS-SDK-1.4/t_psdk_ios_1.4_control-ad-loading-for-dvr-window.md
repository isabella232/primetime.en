---
description: 
seo-description: 
seo-title: Control ad loading for a DVR window
title: Control ad loading for a DVR window
---

# Control ad loading for a DVR window

To control ad loading for a DVR window:

>1. To load all ads for the entire stream, set the `codeph  PTAdMetadata.enableDVRAds` property to `codeph  YES`.
>   The default value is`codeph  NO`, and this option loads ads only from the current live point.
>   For example:
>   
>   ```
>   PTMetadata *metadata = [[[PTMetadata alloc] init] autorelease]; 
>    
>   PTAuditudeMetadata *adMetadata = [[[PTAuditudeMetadata alloc] init] autorelease]; 
>   adMetadata.zoneId = &lt;ZoneId&gt;; 
>   adMetadata.domain = &lt;Domain&gt;; 
>    
>   // Enable DVR Ads by setting to YES the enableDVRAds property on PTAdMetadata 
>   // (PTAuditudeMetadata is a subclass of PTAdMetadata) 
>   adMetadata.enableDVRAds = YES; 
>    
>   [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey]; 
>    
>   //Create PTMediaPlayerItem with the previously prepared metadata 
>   playerItem = [[PTMediaPlayerItem alloc] initWithUrl:url mediaId:yourMediaID metadata:metadata]; 
>   
>   ```
>   
>   
>   
