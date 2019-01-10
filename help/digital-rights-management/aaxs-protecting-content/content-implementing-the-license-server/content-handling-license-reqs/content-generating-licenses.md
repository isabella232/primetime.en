---
seo-title: Generating licenses
title: Generating licenses
uuid: 242d5567-f609-4781-a8a6-2f3d78471344
index: y
internal: n
snippet: y
---

# Generating licenses{#generating-licenses}

To issue a leaf license to the user, the SDK must decrypt the CEK contained in the content metadata and re-encrypt it for the machine requesting a license. To decrypt the CEK, the server must provide information required to decrypt the key. Call `ContentInfo.setKeyRetrievalInfo()` and provide an `AsymmetricKeyRetrieval` object. If the metadata contains multiple policies, the server must determine which policy to use and call `LicenseRequestMessage.setSelectedPolicy()`. Then call `LicenseRequestMessage.generateLicense()` to generate the license. Using the `License` object that is returned, you may modify the expiration or rights in the license.

If an ExternalKeyRetrieval object is specified in the `ContentInfo` object, then the license server is expected to use the associated CEK ID to fetch the appropriate CEK that will be inserted into the license. For more details on how to use the External CEK workflow, see [Adobe Access DRM External CEK Overview](c_aaxs_drm-external-cek-overview.md) 
