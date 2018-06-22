---
description: Your application must provide with the required PTAuditudeMetadata information to connect to the ad server.
seo-description: Your application must provide with the required PTAuditudeMetadata information to connect to the ad server.
seo-title: Set up Primetime ad server metadata
title: Set up Primetime ad server metadata
---

# Set up Primetime ad server metadata

To set up the ad server metadata:

>1. Create an instance of [ `codeph  PTAuditudeMetadata` ](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTAuditudeMetadata.html) and set its properties.
>   ```
>   PTAuditudeMetadata *adMetadata = [[PTAuditudeMetadata alloc] init]; 
>   adMetadata.zoneId = @"INSERT_YOUR_ZONE_ID_HERE"; 
>   adMetadata.domain = @"INSERT_YOUR_DOMAIN_HERE"; 
>   // Optionally set user agent 
>   adMetadata.userAgent = @"INSERT_AGENT_NAME_HERE; 
>   
>   ```
>   
>   
>1. Set the `codeph  PTAuditudeMetadata` instance as metadata for the current `codeph  PTMediaPlayerItem` metadata by using `codeph  PTAdResolvingMetadataKey`.
>   ```
>   // Metadata is an instance of PTMetadata that is used to create the PTMediaPlayerItem 
>   [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey]; 
>   [adMetadata release];
>   ```
>   
>   
>   
