---
description: null
seo-description: null
seo-title: Secure Ad loading over HTTPS
title: Secure Ad loading over HTTPS
uuid: 72096f48-9834-4f55-812e-bdf0dd36dd91
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
