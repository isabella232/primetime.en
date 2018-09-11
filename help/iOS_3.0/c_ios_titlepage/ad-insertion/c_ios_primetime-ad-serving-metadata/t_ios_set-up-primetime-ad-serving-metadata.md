---
description: Your application must provide TVSDK with the required PTAuditudeMetadata information to connect to the ad server.
seo-description: Your application must provide TVSDK with the required PTAuditudeMetadata information to connect to the ad server.
seo-title: Set up Primetime ad server metadata
title: Set up Primetime ad server metadata
uuid: ac5af3a9-1c87-4df0-ae4c-a6cc4f81d829
index: y
internal: n
snippet: y
translate: y
---

# Set up Primetime ad server metadata

Your application must provide TVSDK with the required PTAuditudeMetadata information to connect to the ad server.

To set up the ad server metadata: 

1. Create an instance of [ `PTAuditudeMetadata` ](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTAuditudeMetadata.html) and set its properties.

   ```
   PTAuditudeMetadata *adMetadata = [[PTAuditudeMetadata alloc] init];  
   adMetadata.zoneId = @"INSERT_YOUR_ZONE_ID_HERE"; 
   adMetadata.domain = @"INSERT_YOUR_DOMAIN_HERE"; 
   // Optionally set user agent 
   adMetadata.userAgent = @"INSERT_AGENT_NAME_HERE; 
   
   ```

1. Set the `PTAuditudeMetadata` instance as metadata for the current `PTMediaPlayerItem` metadata by using `PTAdResolvingMetadataKey`.

   ```
   // Metadata is an instance of PTMetadata that is used to create the PTMediaPlayerItem 
   [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey];  
   [adMetadata release];
   ```

Here is an example: 

```
PTMetadata *metadata = [self createMetadata]; 
PTMediaPlayerItem *item =  
  [[[PTMediaPlayerItem alloc] initWithUrl:url mediaId:yourMediaID metadata:metadata] autorelease]; 
 
- (PTMetadata *) createMetadata { 
    PTMetadata* metadata = [[[PTMetadata alloc] init] autorelease]; 
 
    PTAuditudeMetadata *adMetadata = [[[PTAuditudeMetadata alloc] init] autorelease];  
    adMetadata.zoneId = yourZoneID; 
    adMetadata.domain = yourAdServerDomain; 
 
    [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey]; 
 
    return metadata; 
}
```
