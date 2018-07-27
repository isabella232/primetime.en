---
description: To allow the ad resolver to work, ad providers, such as , require configuration values to enable your connection to the provider.
seo-description: To allow the ad resolver to work, ad providers, such as , require configuration values to enable your connection to the provider.
seo-title: Ad insertion metadata
title: Ad insertion metadata
uuid: c5636091-a2ee-47fc-ac3f-9798e936f35a
index: n
internal: n
snippet: y
translate: y
---

# Ad insertion metadata

 <!-- PH element: phrases/primetime-sdk-name --> includes the <!-- PH element: phrases/auditude-name --> library. For your content to include advertising from the <!-- PH element: phrases/auditude-name --> server, your application must provide the following required `AuditudeSettings` information: 
* `mediaID`, which is a unique identifier for the video to be played. The publisher assigns the mediaID when submitting video content and ad information to the  <!-- PH element: phrases/auditude-name-long --> server. This ID is used by <!-- PH element: phrases/auditude-name --> to retrieve related advertising information for the video from the server.

* Your `zoneID`, which is assigned by Adobe, identifies your company or website.
* The domain of your assigned ad server.
* Other targeting parameters. You can include these parameters depending on your needs and the needs of the ad provider.


