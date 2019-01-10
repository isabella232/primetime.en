---
description: Customers can use Adobe Access (AAXS) DRM with their own Content Key Management Systems (CKMS) with the External CEK feature.
seo-description: Customers can use Adobe Access (AAXS) DRM with their own Content Key Management Systems (CKMS) with the External CEK feature.
seo-title: Adobe Access DRM External CEK Overview
title: Adobe Access DRM External CEK Overview
uuid: ea0bba63-7743-4216-863f-392500998eb6
---

# Adobe Access DRM External CEK Overview{#adobe-access-drm-external-cek-overview}

Customers can use Adobe Access (AAXS) DRM with their own Content Key Management Systems (CKMS) with the External CEK feature.

Adobe Access (AAXS) DRM, by default, abstracts out the need to directly handle keys, certificates, and DRM metadata during the content packaging process. The AAXS Java SDK will automatically generate a random Content Encryption Key (CEK) during packaging time, and use it to encrypt the content. Next the SDK encrypts the CEK itself, and inserts it into the content's metadata. At license issuance time, the AAXS server only needs its AAXS license server private key to access the CEK from the metadata to generate a license.
