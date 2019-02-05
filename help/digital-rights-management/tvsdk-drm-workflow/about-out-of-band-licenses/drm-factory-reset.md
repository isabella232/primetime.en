---
seo-title: DRM factory reset
title: DRM factory reset
uuid: 4c009e3d-980a-470e-a4b2-ba878acfb669
---

# DRM factory reset{#drm-factory-reset}

When the user of the device invokes the DRM factory reset option, the device certificate will be purged. To continue playing the protected content, the application must go through the device registration procedure again. If the application sends an outdated pre-generated license, the Primetime DRM client will reject it since the license was encrypted for an older device ID.

* Flash API: [DRMManager.resetDRMVouchers()](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/drm/DRMManager.html#resetDRMVouchers()) - (Can only be called in response to certain un-recoverable DRM error codes.) 
* iOS API: [DRMManager resetDRM](https://help.adobe.com/en_US/primetime/api/drm-apis/client/ios/interface_d_r_m_manager.html#a0dd6c9662428583196e0419d3ea69446) 
* Android API: [DRMManager.resetDRM()](https://help.adobe.com/en_US/primetime/api/drm-apis/client/android/com/adobe/ave/drm/DRMManager.html#resetDRM(com.adobe.ave.drm.DRMOperationErrorCallback,%20com.adobe.ave.drm.DRMOperationCompleteCallback))

