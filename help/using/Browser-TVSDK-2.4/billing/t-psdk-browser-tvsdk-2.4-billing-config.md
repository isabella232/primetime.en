---
description: If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the BillingMetricsConfiguration class to set these parameters up before initializing the media player.
seo-description: If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the BillingMetricsConfiguration class to set these parameters up before initializing the media player.
seo-title: Configure billing metrics
title: Configure billing metrics
uuid: 6edfd375-4a94-4248-be8a-8a382492b0ad
index: y
internal: n
snippet: y
---

# Configure billing metrics{#configure-billing-metrics}

If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the BillingMetricsConfiguration class to set these parameters up before initializing the media player.

Most customers should use the default configuration.

>[!IMPORTANT]
>
>The configuration you set remains in effect for the life of the media player. Once you initialize the media player, you cannot change the configuration.

To configure billing metrics: 

1. Enter the following code sample.

   ```js
   var config = new AdobePSDK.MediaPlayerItemConfig(); 
   config.billingMetricsConfiguration.isEnabled = true; 
   config.billingMetricsConfiguration.proVODBillableDurationMinutes = 60; 
   config.billingMetricsConfiguration.stdVODBillableDurationMinutes = 30; 
   config.billingMetricsConfiguration.liveBillableDurationMinutes = 15; 
   _player.replaceCurrentResource(_resource, config);
   ```

   where `_player` is an instance of `AdobePSDK.MediaPlayer` and `_resource` is an instance of `AdobePSDK.MediaResource`. 

