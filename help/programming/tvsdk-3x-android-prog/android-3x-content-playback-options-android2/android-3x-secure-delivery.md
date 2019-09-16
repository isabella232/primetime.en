---
description: TVSDK introduces secure delivery over HTTPS.
seo-description: TVSDK introduces secure delivery over HTTPS.
seo-title: Secure Delivery over HTTPS
title: Secure Delivery over HTTPS
---

# Secure Delivery over HTTPS {#secure-delivery-https}

Adobe Primetime TVSDK provides an option to enable all the calls originating from TVSDK to be requested over HTTPS, which include 

* Auditude Ad Server Calls
* CRS requests
* DRM licence calls
* Video Analytics Pings
* Billing Pings

In order to use this feature, ensure that the servers configured for serving the above requests should support HTTPS.

This feature is not enabled by default. Use the following to enable secure delivery before call to `MediaPlayer.replaceCurrentResource()`

```java
MediaPlayerItemConfig config = new MediaPlayerItemConfig(context);
NetworkConfiguration netConfig  = new NetworkConfiguration();
netConfig.setForceHTTPS(true);
config.setNetworkConfiguration(netConfig);
```