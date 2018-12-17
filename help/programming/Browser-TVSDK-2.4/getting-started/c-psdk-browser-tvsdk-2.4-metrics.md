---
description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
seo-description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
seo-title: Metrics
title: Metrics
uuid: 0c688a42-4ebb-458b-aa4d-b069c9523bf1
index: y
internal: n
snippet: y
---

# Metrics{#metrics}

Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.

For example: 

```js
var qosProvider = new AdobePSDK.QOSProvider(); 
qosProvider.attachMediaPlayer(player); 
var metrics = qosProvider.playbackInformation;
```

