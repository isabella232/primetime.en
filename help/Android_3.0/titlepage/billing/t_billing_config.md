---
description: If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the BillingMetricsConfiguration class to set these parameters up before initializing the media player.
seo-description: If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the BillingMetricsConfiguration class to set these parameters up before initializing the media player.
seo-title: Configure billing metrics
title: Configure billing metrics
uuid: c89f8506-1bc3-41d8-ba9e-dd6113644649
index: y
internal: n
snippet: y
translate: y
---

# Configure billing metrics

If you use the default configuration, there is nothing else you need to do to enable or configure billing. If you obtained different configuration parameters from your Adobe Enablement representative, use the BillingMetricsConfiguration class to set these parameters up before initializing the media player.


>[!TIP]
>
>Most customers should use the default configuration.

>[!IMPORTANT]
>
>The configuration you set remains in effect for the life of the media player. Once you initialize the media player, you cannot change the configuration.
To configure billing metrics: 

1. Enter the following code sample.

   ```
   java   MediaPlayerItemConfig config = new MediaPlayerItemConfig(); 
   BillingMetricsConfiguration billingConfig = new BillingMetricsConfiguration(); 
   billingConfig.setEnabled(true); 
   billingConfig.setProVODBillableDurationMinutes(60); 
   billingConfig.setStdVODBillableDurationMinutes(30); 
   billingConfig.setLiveBillableDurationMinutes(15); 
   config.setBillingMetricsConfiguration(billingConfig); 
   mediaPlayer.replaceCurrentResource(mediaResource, config);
   ```
