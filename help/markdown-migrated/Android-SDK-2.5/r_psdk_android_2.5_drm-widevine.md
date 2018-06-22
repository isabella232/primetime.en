---
---


Call the following `codeph  com.adobe.mediacore.drm.DRMManager` API before starting play:
```java
public static void setProtectionData( 
 String drm, 
 String licenseServerURL, 
 Map&lt;String, String&gt; requestProperties)
```
Arguments:
* `codeph  drm` - `codeph  "com.widevine.alpha"` for Widevine.
* `codeph  licenseServerURL` - The URL of the Widevine license server that receives license requests.
* `codeph  requestProperties` - Contains extra headers to include in the outgoing license request.
For example, when using content packaged for Expressplay DRM, use the following code before playing:
```java
DRMManager.setProtectionData( 
 "com.widevine.alpha", 
 "https://wv.service.expressplay.com/hms/wv/rights/?ExpressPlayToken= 
<i>token</i>", 
 null); 

```

