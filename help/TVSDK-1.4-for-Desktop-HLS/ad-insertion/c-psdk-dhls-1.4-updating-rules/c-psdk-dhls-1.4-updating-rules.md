---
description: You can use the TVSDK configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.
seo-description: You can use the TVSDK configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.
seo-title: Updating ad creative selection rules
title: Updating ad creative selection rules
uuid: 5978b859-1d22-4434-b207-051369f8e781
index: y
internal: n
snippet: y
---

# Updating ad creative selection rules{#updating-ad-creative-selection-rules}

You can use the TVSDK configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.

When your video player makes a request to an ad server, the VAST/VMAP response usually includes multiple ad creatives ( `MediaFile` elements), each of which provides a URL to a different container-codec version. In some cases, ad creatives in the VAST/VMAP response each provide a different bitrate for the ad. If you want to specify your own priority and transformation rules for these ad creatives, you can do so in the [!DNL AdobeTVSDKConfig.json] configuration file.

>[!IMPORTANT]
>
>* Do not change the name of the TVSDK configuration file. The name must remain [!DNL AdobeTVSDKConfig.json]. 
>* This file should be hosted on your content delivery network (CDN). 
>

You can specify two types of rules in [!DNL AdobeTVSDKConfig.json]: *Priority* rules and *Normalize* rules. 
