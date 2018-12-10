---
seo-title: Generating licenses
title: Generating licenses
uuid: ca03e8b9-0a27-4eff-aac1-efa264241df0
index: y
internal: n
snippet: y
---

# Generating licenses{#generating-licenses}

Iyou want to issue a leaf license to a user, the SDK must decrypt the CEK contained in the content metadata and re-encrypt it for the machine requesting a license. To decrypt the CEK, the server must provide information required to decrypt the key. Call `ContentInfo.setKeyRetrievalInfo()` and provide an `AsymmetricKeyRetrieval` object. If the metadata includes multiple policies, the server must determine which policy to use and call `LicenseRequestMessage.setSelectedPolicy()`. Then call `LicenseRequestMessage.generateLicense()` to generate the license. Using the `License` object that is returned, you may modify the expiration or rights in the license.

If an `ExternalKeyRetrieval` object is specified in the `ContentInfo` object, then the license server is expected to use the associated CEK ID to retrieve the appropriate CEK that is inserted into the license.

See the [Adobe Primetime DRM External CEK Overview](http://help.adobe.com/en_US/primetime/drm/5.3/drm_xkey_mgmt/index.html#concept-Adobe_Primetime_DRM_External_CEK_Overview) for more details on how to use the External CEK workflow. 
