---
description: Asymmetric key encryption, also called public key encryption, uses pairs of keys. One key is for encryption, and the other key is for decryption.
seo-description: Asymmetric key encryption, also called public key encryption, uses pairs of keys. One key is for encryption, and the other key is for decryption.
seo-title: Asymmetric key encryption
title: Asymmetric key encryption
uuid: 35c471cc-1500-4855-ac4d-c5dcaa8d91d1
index: y
internal: n
snippet: y
---

# Asymmetric key encryption{#asymmetric-key-encryption}

Asymmetric key encryption, also called public key encryption, uses pairs of keys. One key is for encryption, and the other key is for decryption.

The decryption key, or the *`private key`*, is kept secret; the encryption key, or the *`public key`*, is made available to anyone who is authorized to encrypt content. Anyone with access to the public key can encrypt content. However, only someone with access to the private key can decrypt the content. The private key cannot be reconstructed from the public key.

When you package content, the License Server’s public key is used to encrypt the content encryption key (CEK) in the DRM metadata. You must ensure that only the License Server has access to the License Server's private key. If someone else has the key, they can decrypt and view the content.

>[!CAUTION]
>
>Make sure that you obtain the License Server’s certificate that includes the public key from a trusted source. This way, you can ensure that it is the License Server's key and not a rogue public key. If attackers were to substitute their public key for the License Server's key, they could decrypt your content.

For more information about how to package content, see [Using the Adobe Primetime DRM SDK for Protecting Content](http://help.adobe.com/en_US/primetime/drm/5.3/protecting_content/index.html#DRM-concept-Using_the_Adobe_Primetime_DRM_SDK_for_Protecting_Content). 
