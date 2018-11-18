---
description: To allow the ad resolver to work, ad providers, such as Adobe Primetime ad decisioning, require configuration values to enable your connection to the provider.
seo-description: To allow the ad resolver to work, ad providers, such as Adobe Primetime ad decisioning, require configuration values to enable your connection to the provider.
seo-title: Ad insertion metadata
title: Ad insertion metadata
uuid: 98fe768c-83c4-467a-902c-91b4ac03bc9b
index: y
internal: n
snippet: y
---

# Ad insertion metadata{#ad-insertion-metadata}

To allow the ad resolver to work, ad providers, such as Adobe Primetime ad decisioning, require configuration values to enable your connection to the provider.

TVSDK includes the Primetime ad decisioning library. For your content to include advertising from the Primetime ad decisioning server, your application must provide the following required `AuditudeSettings` information:

* `mediaID`, which is a unique identifier for the video to be played.

  The publisher assigns the mediaID when submitting video content and ad information to the Adobe Primetime ad decisioning server. This ID is used by Primetime ad decisioning to retrieve related advertising information for the video from the server. 

* Your `zoneID`, which is assigned by Adobe, identifies your company or website. 
* The domain of your assigned ad server. 
* Other targeting parameters.

  You can include these parameters depending on your needs and the needs of the ad provider.

