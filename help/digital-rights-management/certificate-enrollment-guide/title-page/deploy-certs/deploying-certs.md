---
seo-title: Deploy certificates
title: Deploy certificates
uuid: adf72b51-be0f-49ec-83f7-152a378b04e6
index: y
internal: n
snippet: y
---

# Deploy certificates{#deploy-certificates}

To avoid having the PFX password available in clear text on the License Server, the Reference Implementation and Adobe Primetime DRM Server for Protected Streaming require the password to be encrypted when specified in the configuration file. See *Using the Primetime DRM Reference Implementations* or *Using the Primetime DRM Server* for Protected Streaming for instructions on running the scrambling utilities. Each of these includes its own scramble utility, and the encrypted passwords are not interchangeable between these two License Server implementations.

To deploy the certificates and scrambled password to your license server, see *Using the Primetime DRM Reference Implementations* or *Using the Primetime DRM Server for Protected Streaming*. 
