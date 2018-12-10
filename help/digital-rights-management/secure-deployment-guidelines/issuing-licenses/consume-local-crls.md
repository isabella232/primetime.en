---
description: To consume locally generated certificate revocation lists (CRLs) and policy update lists, use Adobe Primetime DRM APIs to verify the signature.
seo-description: To consume locally generated certificate revocation lists (CRLs) and policy update lists, use Adobe Primetime DRM APIs to verify the signature.
seo-title: Consuming locally generated CRLs
title: Consuming locally generated CRLs
uuid: d851222f-23a4-4b43-b3c2-72d1b4917f98
index: y
internal: n
snippet: y
---

# Consuming locally generated CRLs{#consuming-locally-generated-crls}

To consume locally generated certificate revocation lists (CRLs) and policy update lists, use Adobe Primetime DRM APIs to verify the signature.

The following APIs verify that the lists have not been tampered with and that the lists were signed by the correct License Server:

* Call [ `RevocationList.verifySignature`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/revocation/RevocationList.html#verifySignature(java.security.cert.X509Certificate)) to check the signature before you provide the [ `RevocationList`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/revocation/RevocationList.html) to any APIs.

  For more information, see [ `RevocationListFactory`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/revocation/RevocationListFactory.html). 

* Call [ `PolicyUpdateList.verifySignature`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/policyupdate/PolicyUpdateList.html#verifySignature(java.security.cert.X509Certificate)) to check the signature before providing the `PolicyUpdateList` to any APIs.

  For more information, see [ `PolicyUpdateList`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/policyupdate/PolicyUpdateList.html).

