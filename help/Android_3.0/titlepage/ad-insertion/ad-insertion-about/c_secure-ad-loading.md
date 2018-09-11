---
description: null
seo-description: null
seo-title: Secure Ad loading over HTTPS
title: Secure Ad loading over HTTPS
uuid: 60d4a06a-cf16-40e9-a885-ba2645af9ea9
index: y
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
