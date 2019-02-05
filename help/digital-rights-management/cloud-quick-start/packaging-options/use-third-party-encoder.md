---
seo-title: Use a third-party encoder
title: Use a third-party encoder
uuid: 8649303c-b8e6-4c02-a8ad-5734af850bfe
---

# Use a third-party encoder{#use-a-third-party-encoder}

Some customers may already have a content preparation pipeline in place, using a hardware or software video encoder (or Adobe Media Server). If this is the case, any product that can currently create Primetime DRM-protected content can package content for Primetime Cloud DRM by using the same configuration settings as the Primetime Cloud DRM Protection Kit. The required information can be obtained from either of the existing configuration files included in the kit: [!DNL config_hls.xml] or [!DNL config_hds.xml].

The relevant configuration items are:

* License Server URL 
* Key Server URL 
* License Server Certificate 
* Transport Certificate

