---
description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
seo-description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
seo-title: Metrics
title: Metrics
uuid: 4734e532-1f83-4691-b1bd-785f78e55d8d
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

