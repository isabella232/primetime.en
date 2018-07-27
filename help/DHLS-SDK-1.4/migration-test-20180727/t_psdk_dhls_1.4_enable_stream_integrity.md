---
description: By enabling stream integrity, you can prevent ad-blocking software from blocking ads.
seo-description: By enabling stream integrity, you can prevent ad-blocking software from blocking ads.
seo-title: Enable stream integrity
title: Enable stream integrity
uuid: 9f44ebb5-b0bb-4fc6-a081-eb4bd3598a0d
index: n
internal: n
snippet: y
translate: y
---

# Enable stream integrity


>1. Set the ` NetworkConfiguration.forceNativeNetworking` property to ` true`.
>    
>       ```
>       var networkConfiguration:NetworkConfiguration =   
>             new NetworkConfiguration(); 
>       networkConfiguration.forceNativeNetworking = true;
>       ```
>       Remember the following: >    
>    * When this property is set to ` true`,  <!-- PH element: phrases/primetime-sdk-name --> sends ad requests through the native networking stack and avoiding ad blockers.
>    * When this property is set to ` false`, ad requests proceed through the browser's network stack as usual. The default is ` false`.

>    
>1. If your application needs to send cookie headers with requests, and stream integrity is enabled, set the header to use the ` NetworkConfiguration.cookieHeaders` property.

>   >[!IMPORTANT]
>   >
>   >When stream integrity is enabled, <!-- PH element: phrases/primetime-sdk-name --> might not have access to cookies that are set in the browser. If your application needs cookies, complete this step to provide the cookie headers to <!-- PH element: phrases/primetime-sdk-name --> .
>
>1. Set your ` NetworkConfiguration` as metadata.

>    
>       ```
>       var resourceMetadata:Metadata = new Metadata(); 
>       resourceMetadata.setMetadata(  
>           DefaultMetadataKeys.NETWORK_CONFIGURATION_KEY,  
>           networkConfiguration);
>       ```
>1. Provide your metadata when you create a ` MediaResource`.
>   For example, if you use ` createFromURL`: >
>   ```
>   var resource:MediaResource = MediaResource.createFromURL(url, resourceMetadata);
>   ```

>   This is needed because ` NetworkConfiguration` is part of the metadata that is loaded in ` MediaResource`. After you call ` replaceCurrentResource(MediaResource, MediaPlayerItemConfig)`, the ` NetworkConfiguration` is automatically applied to the ` MediaPlayerItemConfig` and used by  <!-- PH element: phrases/primetime-sdk-name --> .
>
