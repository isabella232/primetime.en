---
description: You can track video use by integrating with Adobe Analytics.
seo-description: You can track video use by integrating with Adobe Analytics.
seo-title: Video analytics
title: Video analytics
uuid: 494edf1c-9b41-4ab4-818b-9ad6ca1f8d68
index: n
internal: n
snippet: y
translate: y
---

# Video analytics

Video tracking in  <!-- PH element: phrases/primetime-sdk-name --> uses the**Adobe Analytics Video Essentials** service, which provides video engagement metrics, such as video views, video completes, ad impressions, time spent on video, and so on. For more information about this service, contact your Adobe representative. 
The following procedure summarizes the steps to activate video tracking in your player:

1. Initialize and/or configure the following video tracking components: 
    * **AppMeasurement library** - Contains the low-level data collection core logic. This is where the video heartbeat data is accumulated and sent over the network.
    * **Video heartbeat library** - Contains the video-heartbeat data collection core logic. The video heartbeat library accesses a subset of the `AppMeasurement` library APIs. 
      >[!TIP]
      >
      >Your app does not interact directly with the video heartbeat code. Instead, the app uses <!-- PH element: phrases/primetime-sdk-name --> APIs to configure your player's video tracking capabilities.

    * **VisitorID Library** - Uniquely identifies visitors to the web page that hosts the video player.

   >[!IMPORTANT]
   >
   >The <!-- PH element: phrases/primetime-sdk-name --> built-in video tracking capability depends on a properly configured `AppMeasurement` instance. The tracking elements assume that the `AppMeasurement` library is already instantiated and configured before configuring and activating video tracking.  <!-- PH element: phrases/primetime-sdk-name --> video tracking capabilities depend on the existence of a fully functional and properly configured instance of the `AppMeasurement` library. 

1. Set up video analytics reporting on the server side by using Adobe Analytics Admin Tools.
