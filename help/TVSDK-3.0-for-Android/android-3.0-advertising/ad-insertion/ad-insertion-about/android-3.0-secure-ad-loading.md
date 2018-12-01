---
description: null
seo-description: null
seo-title: Secure Ad loading over HTTPS
title: Secure Ad loading over HTTPS
uuid: af4c2301-3a39-42af-a690-e763591f9f28
index: y
internal: n
snippet: y
---

# Secure Ad loading over HTTPS{#secure-ad-loading-over-https}

Adobe Primetime provides an option to request first call to the Primetime ad server and CRS related calls over HTTPS.

The feature is not enabled by default. Use the following to enable secure ad loading.

```
AuditudeSettings auditudeSettings = new AuditudeSettings(); 
auditudeSettings. getForceHttpsConfiguration().setAdServerCalls(true);
```

