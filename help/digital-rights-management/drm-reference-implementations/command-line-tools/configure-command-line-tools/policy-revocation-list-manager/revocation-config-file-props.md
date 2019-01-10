---
description: null
seo-description: null
seo-title: Configuration properties
title: Configuration properties
uuid: 622b323f-f290-4fc4-86ee-e1f7925a4989
index: y
internal: n
snippet: y
---

# Configuration properties{#configuration-properties}

You need to apply credentials to sign revocation lists. The following Revocation List Manager properties specify a PKCS12 file that includes credentials for signing revocation lists (License Server Certificate), along with the password for the cert:

* `revocation.sign.certfile=license-server-credentials.pfx` 
* `revocation.sign.certpass=password`

