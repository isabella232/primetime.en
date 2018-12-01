---
description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
seo-description: Browser TVSDK provides metrics to use for analyzing and debugging. You can get these metrics by using QoSProvider.
seo-title: Metrics
title: Metrics
uuid: e73eb47a-932b-476a-a7a3-e305ece1180d
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

