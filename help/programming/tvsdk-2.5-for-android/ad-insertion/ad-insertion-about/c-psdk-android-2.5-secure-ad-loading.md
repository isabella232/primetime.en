---
description: null
seo-description: null
seo-title: Secure Ad loading over HTTPS
title: Secure Ad loading over HTTPS
uuid: 72ab94d3-ee0c-4f02-adf2-c186ae6aec26
---

# Secure Ad loading over HTTPS{#secure-ad-loading-over-https}

Adobe Primetime provides an option to request first call to the Primetime ad server and CRS related calls over HTTPS.

The feature is not enabled by default. Use the following to enable secure ad loading.

```
AuditudeSettings auditudeSettings = new AuditudeSettings(); 
auditudeSettings. getForceHttpsConfiguration().setAdServerCalls(true);
```

