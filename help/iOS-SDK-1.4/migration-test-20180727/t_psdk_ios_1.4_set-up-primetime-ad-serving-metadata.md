---
description: Your application must provide with the required PTAuditudeMetadata information to connect to the ad server.
seo-description: Your application must provide with the required PTAuditudeMetadata information to connect to the ad server.
seo-title: Set up Primetime ad server metadata
title: Set up Primetime ad server metadata
uuid: ba1c7714-e8fa-457c-a3d5-095a2526d8d2
index: n
internal: n
snippet: y
translate: y
---

# Set up Primetime ad server metadata

To set up the ad server metadata:

>1. Create an instance of [ ` PTAuditudeMetadata` ](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTAuditudeMetadata.html) and set its properties.
>
>   ```
>   PTAuditudeMetadata *adMetadata = [[PTAuditudeMetadata alloc] init];  
>   adMetadata.zoneId = @"INSERT_YOUR_ZONE_ID_HERE"; 
>   adMetadata.domain = @"INSERT_YOUR_DOMAIN_HERE"; 
>   // Optionally set user agent 
>   adMetadata.userAgent = @"INSERT_AGENT_NAME_HERE; 
>   
>   ```
>
>1. Set the ` PTAuditudeMetadata` instance as metadata for the current ` PTMediaPlayerItem` metadata by using ` PTAdResolvingMetadataKey`.
>
>   ```
>   // Metadata is an instance of PTMetadata that is used to create the PTMediaPlayerItem 
>   [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey];  
>   [adMetadata release];
>   ```
>
