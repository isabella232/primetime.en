---
seo-title: Configure SSL on your BEES server
title: Configure SSL on your BEES server
uuid: 041a106e-8b21-4018-815d-b7ea48c3de03
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
