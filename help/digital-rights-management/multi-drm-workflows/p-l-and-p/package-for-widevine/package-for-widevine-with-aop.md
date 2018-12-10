---
description: Adobe Offline Packager takes as input unencrypted mp4 content.
seo-description: Adobe Offline Packager takes as input unencrypted mp4 content.
seo-title: Package your content with Adobe Offline Packager
title: Package your content with Adobe Offline Packager
uuid: 02196022-669d-424b-9538-955d54842595
index: y
internal: n
snippet: y
---

# Package your content with Adobe Offline Packager{#package-your-content-with-adobe-offline-packager}

Adobe Offline Packager takes as input unencrypted mp4 content.

1. **Calling Adobe Offline Packager**

   A typical adobe offline packager invocation would look like the call below: 
   In this particular case the offline packager is adding both Widevine content protection and PlayReady content protection initialization data to the output DASH content. The value of `-key_file_path` is for a base64-encoded key. The value of `-playready_LA_URL` is for PlayReady license acqusition.

   The conf_path argument points to configuration file that would contain the following: 
   Because certain Android devices — primarily Amazon Fire TV — do not support audio decryption, audio encryption is optional. 

