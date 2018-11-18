---
description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
seo-description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
seo-title: Metrics
title: Metrics
uuid: e8cf6c08-aab1-4273-96cb-90954e7ef447
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

