---
seo-title: Generating licenses
title: Generating licenses
uuid: f91b0cc8-e0ed-4722-947b-22eb2bfba916
index: y
internal: n
snippet: y
---

# Generating licenses{#generating-licenses}

If you want to issue a leaf license to a user, the SDK must decrypt the CEK contained in the content metadata and re-encrypt it for the machine requesting a license. To decrypt the CEK, the server must provide information required to decrypt the key. Call `ContentInfo.setKeyRetrievalInfo()` and provide an `AsymmetricKeyRetrieval` object. If the metadata includes multiple policies, the server must determine which policy to use and call `LicenseRequestMessage.setSelectedPolicy()`. Then call `LicenseRequestMessage.generateLicense()` to generate the license. Using the `License` object that is returned, you may modify the expiration or rights in the license.

If an `ExternalKeyRetrieval` object is specified in the `ContentInfo` object, then the license server is expected to use the associated CEK ID to retrieve the appropriate CEK that is inserted into the license.

See the [Adobe Primetime DRM External CEK Overview](https://help.adobe.com/en_US/primetime/drm/5.3/drm_xkey_mgmt/index.html#concept-Adobe_Primetime_DRM_External_CEK_Overview) for more details on how to use the External CEK workflow. 
