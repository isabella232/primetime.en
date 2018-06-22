---
description: You can use the configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.
keywords: creative selection rules;AdobeTVSDKConfig;ad creative priorities;transformation rules
seo-description: You can use the configuration file (AdobeTVSDKConfig.json) to update the priorities for ad creative selection on VAST/VMAP responses. You can also use this configuration file to define the source URL transformation rules for ad creatives.
seo-title: Updating ad creative selection rules
title: Updating ad creative selection rules
---

# Updating ad creative selection rules



When your video player makes a request to an ad server, the VAST/VMAP response usually includes multiple ad creatives ( `codeph  MediaFile` elements), each of which provides a URL to a different container-codec version. In some cases, ad creatives in the VAST/VMAP response each provide a different bitrate for the ad. If you want to specify your own priority and transformation rules for these ad creatives, you can do so in the `filepath  AdobeTVSDKConfig.json` configuration file.


>[!IMPORTANT]
>
>* Do not change the name of the  configuration file. The name must remain `filepath  AdobeTVSDKConfig.json`.
>* This file must be placed in the `filepath  assets/` folder of your project.
>* Changing audio tracks when ad is playing does not change the audio track. A player should not allow users to change the audio track when an ad is playing.
>

You can specify two types of rules in `filepath  AdobeTVSDKConfig.json`: *Priority* rules and *Normalize* rules.

`uicontrol  Ad Rules change`

<a id="section_EDCE7C94156D4A47AA2FBAE9BE0390CE"></a>

The Ad rules are specified using a JSON file. The format of the JSON file remains the same in both versions of the TVSDK. However, in TVSDK v2.5, the Ad rules JSON file must be hosted on a location accessible via a HTTP URL. The application can use an instance of AuditudeSettings:


```
//TVSDK v2.5 AuditudeSettings result = new AuditudeSettings(); 
result.setCRSRulesJsonURL(&lt;http url of 
AdobeTVSDKConfig.json&gt;); 

```



