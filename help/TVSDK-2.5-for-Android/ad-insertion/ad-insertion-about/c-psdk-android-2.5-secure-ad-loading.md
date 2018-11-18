---
description: null
seo-description: null
seo-title: Secure Ad loading over HTTPS
title: Secure Ad loading over HTTPS
uuid: 1aae6a63-9d64-4a54-b8e9-2e80ca6bcc7a
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

