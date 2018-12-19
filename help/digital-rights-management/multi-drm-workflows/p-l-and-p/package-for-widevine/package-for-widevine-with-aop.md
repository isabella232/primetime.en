---
description: Adobe Offline Packager takes as input unencrypted mp4 content.
seo-description: Adobe Offline Packager takes as input unencrypted mp4 content.
seo-title: Package your content with Adobe Offline Packager
title: Package your content with Adobe Offline Packager
uuid: d0676147-c20f-49ea-93a6-9c8dbbbba992
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

