---
seo-title: Configure SSL on your BEES server
title: Configure SSL on your BEES server
uuid: 05d1a3b7-b253-4ee3-bf87-20ae2d78c6ac
index: y
internal: n
snippet: y
---

# Configure SSL on your BEES server{#configure-ssl-on-your-bees-server}

1. Provide your server SSL certificate to your Adobe contact who supplied this software.

   The certificate will be added as a trusted certificate to the  Primetime Cloud DRM trust store.
1. To enable client authentication for the SSL connection (disabled in this version):
   1. Add the [!DNL clouddrm-transport.cer] and [!DNL AdobeFlashAccessIntermediateCA.cer] certificates to the trust store used for client authentication.
   1. Enable client authentication in your SSL configuration.
