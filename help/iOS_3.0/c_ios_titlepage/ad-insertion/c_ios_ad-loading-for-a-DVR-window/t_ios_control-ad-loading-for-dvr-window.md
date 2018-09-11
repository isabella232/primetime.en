---
description: null
seo-description: null
seo-title: Control ad loading for a DVR window
title: Control ad loading for a DVR window
uuid: 08387ecc-b101-409e-9850-db1512b568e0
index: y
internal: n
snippet: y
translate: y
---

# Control ad loading for a DVR window

To control ad loading for a DVR window: 

1. To load all ads for the entire stream, set the `PTAdMetadata.enableDVRAds` property to `YES`.

   The default value is `NO`, and this option loads ads only from the current live point. For example: 

   ```
   PTMetadata *metadata = [[[PTMetadata alloc] init] autorelease]; 
    
   PTAuditudeMetadata *adMetadata = [[[PTAuditudeMetadata alloc] init] autorelease];  
   adMetadata.zoneId = <ZoneId>; 
   adMetadata.domain = <Domain>; 
    
   // Enable DVR Ads by setting to YES the enableDVRAds property on PTAdMetadata  
   // (PTAuditudeMetadata is a subclass of PTAdMetadata)  
   adMetadata.enableDVRAds = YES; 
    
   [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey]; 
    
   //Create PTMediaPlayerItem with the previously prepared metadata    
   playerItem = [[PTMediaPlayerItem alloc] initWithUrl:url mediaId:yourMediaID metadata:metadata]; 
   
   ```

