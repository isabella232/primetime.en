---
description: You can use Adobe Primetime DRM to create CRLs that supplement the machine CRL that is published by Adobe.
seo-description: You can use Adobe Primetime DRM to create CRLs that supplement the machine CRL that is published by Adobe.
seo-title: Generating CRLs to supplement those published by Adobe
title: Generating CRLs to supplement those published by Adobe
uuid: 0cc4254d-20a0-4e05-9c5b-0b84a5c833cb
index: y
internal: n
snippet: y
---

# Generating CRLs to supplement those published by Adobe{#generating-crls-to-supplement-those-published-by-adobe}

You can use Adobe Primetime DRM to create CRLs that supplement the machine CRL that is published by Adobe.

The Primetime DRM SDK checks and enforces the Adobe CRLs. However, you can disallow additional client machines by creating a CRL that revokes additional machine credentials by passing the CRL to the Primetime DRM SDK. When you issue a license, the SDK checks the Adobe CRL and your CRL.

To generate CRLs, see [ `RevocationListFactory`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/revocation/RevocationListFactory.html). 
