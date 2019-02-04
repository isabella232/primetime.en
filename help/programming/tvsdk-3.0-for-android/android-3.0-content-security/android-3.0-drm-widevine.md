---
description: You can use the features of the Primetime Digital Rights Management (DRM) system to provide secure access to your video content. Alternatively, you can use third-party DRM solutions as an alternative to Adobe's integrated solution.
seo-description: You can use the features of the Primetime Digital Rights Management (DRM) system to provide secure access to your video content. Alternatively, you can use third-party DRM solutions as an alternative to Adobe's integrated solution.
seo-title: Widevine DRM
title: Widevine DRM
uuid: 3a5fd786-4319-4e92-83b6-0f5328df6a44
index: y
internal: n
snippet: y
---

# Widevine DRM{#widevine-drm}

You can use the features of the Primetime Digital Rights Management (DRM) system to provide secure access to your video content. Alternatively, you can use third-party DRM solutions as an alternative to Adobe's integrated solution.

Contact your Adobe representative for the most up-to-date information on the availability of third-party DRM solutions.

<!--<a id="section_1385440013EF4A9AA45B6AC98919E662"></a>-->

You can use the Android native Widevine DRM with DASH streams.

Call the following `com.adobe.mediacore.drm.DRMManager` API before starting play: 

```java
public static void setProtectionData( 
    String drm,  
    String licenseServerURL,   
    Map<String, String> requestProperties)
```

Arguments:

* `drm` - `"com.widevine.alpha"` for Widevine. 

* `licenseServerURL` - The URL of the Widevine license server that receives license requests. 
* `requestProperties` - Contains extra headers to include in the outgoing license request.

For example, when using content packaged for Expressplay DRM, use the following code before playing: 

```java
DRMManager.setProtectionData( 
  "com.widevine.alpha",  
  "https://wv.service.expressplay.com/hms/wv/rights/?ExpressPlayToken= 
<i>token</i>",  
  null); 

```

