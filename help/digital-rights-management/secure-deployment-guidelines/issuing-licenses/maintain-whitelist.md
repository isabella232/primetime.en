---
description: A whitelist is a list of trusted entities.
seo-description: A whitelist is a list of trusted entities.
seo-title: Maintain a whitelist of trusted content packagers
title: Maintain a whitelist of trusted content packagers
uuid: 9a132ef9-eb56-408a-939e-1acd32d83a33
---

# Maintain a whitelist of trusted content packagers{#maintain-a-whitelist-of-trusted-content-packagers}

A whitelist is a list of trusted entities.

For content packagers, the entities are organizations that are trusted by the content owner to package (or encrypt) the video files and create DRM protected content. When deploying Adobe Primetime DRM, you should maintain a whitelist of trusted content packagers. You must also verify the identity of the content packager in the DRM metadata of a DRM protected file before issuing a license.

To learn how to obtain information about the entity that packaged the content, see [V2ContentMetaData.getPackagerInfo()](https://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/media/drm/keys/v2/V2ContentMetaData.html#getPackagerInfo()). 
