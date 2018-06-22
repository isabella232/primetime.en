---
description: You can use to send arbitrary data in cookie headers for session management, gate access, and so on.
seo-description: You can use to send arbitrary data in cookie headers for session management, gate access, and so on.
seo-title: Work with cookies
title: Work with cookies
---

# Work with cookies

Here is a example with some type of authentication when making requests to the key server:
1. Your customer logs into your website in a browser and their login shows that they are allowed to view content.
1. Your application generates an authentication token, based on what is expected by the license server. Pass that value to .
1. sets that value in the cookie header.
1. When  makes a request to the key server to get a key to decrypt the content, that request contains the authentication value in the cookie header, so the key server knows that the request is valid.

To work with cookies:

>1. Use the `codeph  cookieHeaders` property in `codeph  NetworkConfiguration` to set a cookie. The `codeph  cookieHeaders` property is a Metadata object, and you can add key value pairs to this object to be included in the cookie header.
>   For example:
>   
>   ```
>   var metadata:Metadata = new Metadata(); 
>   metadata.setValue(“val1”, “12345”); 
>   metadata.setValue(“val2”, “abcd”); 
>    
>   networkConfiguration.cookieHeaders = metadata;
>   ```
>   By default, cookie headers are sent only with key requests. To send cookie headers with all requests, set the `codeph  NetworkConfiguration` property `codeph  useCookieHeadersForAllRequests` to true.
>   
>   
>   
>1. To ensure that `codeph  NetworkConfiguration` works, set it as metadata:
>   ```
>   var networkConfiguration:NetworkConfiguration = new NetworkConfiguration(); 
>   networkConfiguration.forceNativeNetworking = true; 
>   var resourceMetadata:Metadata = new Metadata(); 
>   resourceMetadata.setMetadata(DefaultMetadataKeys.NETWORK_CONFIGURATION_KEY, 
>    networkConfiguration);
>   ```
>   
>   
>1. Provide the metadata from the previous step when you create a `codeph  MediaResource`.
>   For example, if you use the `codeph  createFromURL` method, enter the following information:
>   ```
>   var resource:MediaResource = MediaResource.createFromURL(url, resourceMetadata);
>   ```
>   
>   
>   
>   
