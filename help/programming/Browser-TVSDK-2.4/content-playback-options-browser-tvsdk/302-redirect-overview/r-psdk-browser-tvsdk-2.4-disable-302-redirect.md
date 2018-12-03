---
description: You can use the useRedirectedUrl property to enable 302 redirect (true) or disable (false).
seo-description: You can use the useRedirectedUrl property to enable 302 redirect (true) or disable (false).
seo-title: Disabling 302 redirect optimization
title: Disabling 302 redirect optimization
uuid: 94c3d8f8-e725-4fd7-8d7d-a7336ee3055d
index: y
internal: n
snippet: y
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

