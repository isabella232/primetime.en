---
description: To allow the ad resolver to work, ad providers, such as , require configuration values to enable your connection to the provider.
seo-description: To allow the ad resolver to work, ad providers, such as , require configuration values to enable your connection to the provider.
seo-title: Ad insertion metadata
title: Ad insertion metadata
---

# Ad insertion metadata

includes the  library. For your content to include advertising from the  server, your application must provide the following required `codeph AuditudeSettings` information:
* `codeph mediaID`, which is a unique identifier for the video to be played.
  The publisher assigns the mediaID when submitting video content and ad information to the  server. This ID is used by  to retrieve related advertising information for the video from the server.
  
  
* (Optional)`codeph defaultMediaId`, which specifies the ads that are served when the following conditions are met:
    * Your request to the ad server is invalid, or the content is incorrectly configured.
    * is experiencing delays in propagating the data.
    * One of the  back-end processes is malfunctioning or is unavailable.
  >[!TIP]
  >
  >Adobe recommends using`codeph defaultMediaId`.
  
* Your `codeph zoneID`, which is assigned by Adobe, identifies your company or website.
* The domain of your assigned ad server.
* Other targeting parameters.
  You can include these parameters depending on your needs and the needs of the ad provider.
  
  

