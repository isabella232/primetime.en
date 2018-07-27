---
description: The Primetime player supports AAXS integration as custom DRM workflows. This means that your application must implement the DRM authentication workflows before playing the stream.
seo-description: The Primetime player supports AAXS integration as custom DRM workflows. This means that your application must implement the DRM authentication workflows before playing the stream.
seo-title: DRM content protection
title: DRM content protection
uuid: d9db4ada-5544-4f5f-b935-5ea8afd2aec1
index: n
internal: n
snippet: y
translate: y
---

# DRM content protection

To enable this,  provides you with the DRM manager for authentication. The reference implementation provides an example of the following workflows: 
* How to load and play back HLS streams with Access content protection, optimized for low error rates and quick start up.
* How to load and play back HLS streams with AES128 content protection.
* How to load and play back HLS streams with PHLS content protection, optimized for low error rates and quick start up.

All DRM-protected content is handled automatically by the DRM libraries built into the . However, you can expose error handling, optimization of device individualization, and license acquisition using  API callbacks. 
