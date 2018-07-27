---
description: null
seo-description: null
seo-title: Secure Ad loading over HTTPS
title: Secure Ad loading over HTTPS
uuid: d2d7c54e-ec7f-453a-a5f2-d98b0a826574
index: n
internal: n
snippet: y
translate: y
---

# Secure Ad loading over HTTPS

Adobe Primetime provides an option to request first call to the Primetime ad server and CRS related calls over HTTPS.
The feature is not enabled by default. Use the following to enable secure ad loading.

```
AuditudeSettings auditudeSettings = new AuditudeSettings(); 
auditudeSettings. getForceHttpsConfiguration().setAdServerCalls(true);
```
