---
description: You can use the configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.
keywords: creative selection rules;AdobeTVSDKConfig;ad creative priorities;transformation rules
seo-description: You can use the configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.
seo-title: Updating ad creative selection rules
title: Updating ad creative selection rules
uuid: 1b31359e-69e5-4a7e-a907-b95258b2a5f3
index: n
internal: n
snippet: y
translate: y
---

# Updating ad creative selection rules


When your video player makes a request to an ad server, the VAST/VMAP response usually includes multiple ad creatives ( `MediaFile` elements), each of which provides a URL to a different container-codec version. In some cases, ad creatives in the VAST/VMAP response each provide a different bitrate for the ad. If you want to specify your own priority and transformation rules for these ad creatives, you can do so in the `AdobeTVSDKConfig.json` configuration file.

>[!IMPORTANT]
>
>
>* Do not change the name of the  <!-- PH element: phrases/primetime-sdk-name --> configuration file. The name must remain `AdobeTVSDKConfig.json`.
>* This file should be hosted on your content delivery network (CDN).



You can specify two types of rules in `AdobeTVSDKConfig.json`: *Priority* rules and *Normalize* rules.
