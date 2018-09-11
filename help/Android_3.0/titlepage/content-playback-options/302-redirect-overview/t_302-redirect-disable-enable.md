---
description: Use the useRedirectedUrl property to turn 302 redirect on (true) or off (false).
seo-description: Use the useRedirectedUrl property to turn 302 redirect on (true) or off (false).
seo-title: Disable or enable 302 redirect optimization
title: Disable or enable 302 redirect optimization
uuid: 8aa79c66-606e-425c-a69a-7bfa764d43b3
index: y
internal: n
snippet: y
translate: y
---

# Disable or enable 302 redirect optimization

Use the useRedirectedUrl property to turn 302 redirect on (true) or off (false).

For example:
```
java// Set useRedirectedUrl property to false 
NetworkConfiguration networkConfiguration = new NetworkConfiguration(); 
networkConfiguration.setUseRedirectedUrl(false); 
 
//Set NetworkConfiguration on MediaPlayerItemConfig 
MediaPlayerItemConfig config = new MediaPlayerItemConfig (); 
config.setNetworkConfiguration(networkConfiguration); 
 
//Use this config when loading the MediaPlayerItem or calling replaceCurrentResource
```
