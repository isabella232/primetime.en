---
description: By enabling stream integrity, you can prevent ad-blocking software from blocking ads.
seo-description: By enabling stream integrity, you can prevent ad-blocking software from blocking ads.
seo-title: Enable stream integrity
title: Enable stream integrity
---

# Enable stream integrity

>1. Set the `codeph  NetworkConfiguration.forceNativeNetworking` property to `codeph  true`.
>   ```
>   var networkConfiguration:NetworkConfiguration = 
>    new NetworkConfiguration(); 
>   networkConfiguration.forceNativeNetworking = true;
>   ```
>   Remember the following:
>* When this property is set to `codeph  true`,  sends ad requests through the native networking stack and avoiding ad blockers.
>* When this property is set to `codeph  false`, ad requests proceed through the browser's network stack as usual. The default is `codeph  false`.
>   
>   
>   
>1. If your application needs to send cookie headers with requests, and stream integrity is enabled, set the header to use the `codeph  NetworkConfiguration.cookieHeaders` property.
>   >[!IMPORTANT]
>   >
>   >When stream integrity is enabled, might not have access to cookies that are set in the browser. If your application needs cookies, complete this step to provide the cookie headers to .
>   
>   
>1. Set your `codeph  NetworkConfiguration` as metadata.
>       
>       ```
>       var resourceMetadata:Metadata = new Metadata(); 
>       resourceMetadata.setMetadata( 
>        DefaultMetadataKeys.NETWORK_CONFIGURATION_KEY, 
>        networkConfiguration);
>       ```
>       
>   
>1. Provide your metadata when you create a `codeph  MediaResource`.
>   For example, if you use `codeph  createFromURL`:
>   ```
>   var resource:MediaResource = MediaResource.createFromURL(url, resourceMetadata);
>   ```
>   
>   This is needed because `codeph  NetworkConfiguration` is part of the metadata that is loaded in `codeph  MediaResource`. After you call `codeph  replaceCurrentResource(MediaResource, MediaPlayerItemConfig)`, the `codeph  NetworkConfiguration` is automatically applied to the `codeph  MediaPlayerItemConfig` and used by .
>   
>   
>   
>   
