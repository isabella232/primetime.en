---
seo-title: Authentication workflow details
title: Authentication workflow details
uuid: 3ba4b635-b195-477c-9113-d12eca1c25fb
index: y
internal: n
snippet: y
---

# Authentication workflow details{#authentication-workflow-details}

In order for your BEES endpoint to make entitlement decisions, the client device must provide authentication information. You accomplish this by using your own customer-specific authentication token.

Primetime Cloud DRM  does not have to understand this token - it simply passes this token through to your BEES endpoint. The client device is responsible for creating or acquiring this token and setting it using the `DRMManager.setAuthenticationToken()` API.

To associate this token with  Primetime Cloud DRM , so that it is sent with the license request: 

1. Instantiate the `DRMManager` object with the DRM metadata of the content that was packaged for  Primetime Cloud DRM .

   The `setAuthenticationToken()` method works by associating the given byte array with the License Server URL provided in the DRM metadata that was used to instantiate `DRMManager`.

   ```java
   //client device acquires auth token needed by your BEES endpoint  
   DRMManager mgr = new DRMManager(<DRM Metadata of CloudDRM content>);  
   mgr.setAuthenticationToken(<auth token>);
   ```

>The token gets sent with all license requests until the token is cleared by calling `.setAuthenticationToken` with null as the parameter. 
