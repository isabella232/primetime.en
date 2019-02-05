---
description: You can use the useRedirectedUrl property to enable 302 redirect (true) or disable (false).
seo-description: You can use the useRedirectedUrl property to enable 302 redirect (true) or disable (false).
seo-title: Disabling 302 redirect optimization
title: Disabling 302 redirect optimization
uuid: e9d07f61-ef64-43c7-a2f0-f46b33308672
---

# Disabling 302 redirect optimization{#disabling-redirect-optimization}

You can use the useRedirectedUrl property to enable 302 redirect (true) or disable (false).

For example: 

```js
var networkConfiguration = new AdobePSDK.NetworkConfiguration(); 
networkConfiguration.useRedirectedUrl = false; 
 
var config = new AdobePSDK.MediaPlayerItemConfig(); 
config.networkConfiguration = networkConfiguration;; 
 
player.replaceCurrentResource(mediaResource, config);
```

