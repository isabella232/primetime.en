---
description: You can use the configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.
keywords: creative selection rules;AdobeTVSDKConfig;ad creative priorities;transformation rules
seo-description: You can use the configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.
seo-title: Updating ad creative selection rules
title: Updating ad creative selection rules
---

# Updating ad creative selection rules



When your video player makes a request to an ad server, the VAST/VMAP response usually includes multiple ad creatives (`codeph MediaFile` elements), each of which provides a URL to a different container-codec version. In some cases, ad creatives in the VAST/VMAP response each provide a different bitrate for the ad. If you want to specify your own priority and transformation rules for these ad creatives, you can do so in the `filepath AdobeTVSDKConfig.json` configuration file.


>[!IMPORTANT]
>
>* Do not change the name of the  configuration file. The name must remain `filepath AdobeTVSDKConfig.json`.
>* This file should be hosted on your content delivery network (CDN).
>

You can specify two types of rules in `filepath AdobeTVSDKConfig.json`: *Priority* rules and *Normalize* rules.

