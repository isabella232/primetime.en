---
description: You can use the Android native Widevine DRM with DASH streams.
seo-description: You can use the Android native Widevine DRM with DASH streams.
seo-title: Widevine DRM
title: Widevine DRM
uuid: 4848fe19-ff87-4ba9-8b92-32ea90a1107c
index: y
internal: n
snippet: y
translate: y
---

# Widevine DRM

You can use the Android native Widevine DRM with DASH streams.




Call the following `com.adobe.mediacore.drm.DRMManager` API before starting play: 
```
javapublic static void setProtectionData( 
    String drm,  
    String licenseServerURL,   
    Map<String, String> requestProperties)
```
Arguments:
* `drm` - `"com.widevine.alpha"` for Widevine.
* `licenseServerURL` - The URL of the Widevine license server that receives license requests.
* `requestProperties` - Contains extra headers to include in the outgoing license request.


For example, when using content packaged for Expressplay DRM, use the following code before playing:
```
javaDRMManager.setProtectionData( 
  "com.widevine.alpha",  
  "https://wv.service.expressplay.com/hms/wv/rights/?ExpressPlayToken= 
<i>token</i>",  
  null); 

```

