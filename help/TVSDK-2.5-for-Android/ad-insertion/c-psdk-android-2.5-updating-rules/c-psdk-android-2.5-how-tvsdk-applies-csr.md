---
description: null
keywords: creative selection rules;AdobeTVSDKConfig
seo-description: null
seo-title: Apply creative selection rules
title: Apply creative selection rules
uuid: f587ce39-740b-4410-a132-da680d89ace5
index: y
internal: n
snippet: y
---

# Apply creative selection rules{#apply-creative-selection-rules}

TVSDK applies creative selection rules in the following ways:

* TVSDK applies all `default` rules first, followed by the zone-specific rules. 
* TVSDK ignores any rules that are not defined for the current zone ID.
* Once TVSDK applies the default rules, the zone-specific rules can further change the creative priorities based on the `host` (domain) matches on the creative selected by the `default` rules.

* In the included sample rules file with additional zone rules, once TVSDK applies the `default` rules, if the M3U8 creative domain does not contain [!DNL my.domain.com] or [!DNL a.bcd.com] and the ad zone is `1234`, the creatives are re-ordered and the Flash VPAID creative is played first if available. Otherwise an MP4 ad is played, and so on down to JavaScript.

* If an ad creative is selected that TVSDK cannot play natively ( [!DNL .mp4], [!DNL .flv], etc.), TVSDK issues a repackaging request.

Note that the ad types that can be handled by TVSDK are still defined through the `validMimeTypes` setting in `AuditudeSettings`.

<!-- 

In Android 2.5 API docs, I see a 
<span class="codeph"> setValidMimeTypes</span> but not a 
<span class="codeph"> getValidMimeTypes</span>.

 -->

