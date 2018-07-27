---
description: null
keywords: creative selection rules;AdobeTVSDKConfig
seo-description: null
seo-title: Applying creative selection rules
title: Applying creative selection rules
uuid: 127e55c1-8aeb-4a96-b635-03a9749dd9a4
index: n
internal: n
snippet: y
translate: y
---

# Applying creative selection rules

TVSDK applies creative selection rules in the following ways:

* <!-- PH element: phrases/primetime-sdk-name --> applies all `default` rules first, followed by the zone-specific rules.
* <!-- PH element: phrases/primetime-sdk-name --> ignores any rules that are not defined for the current zone ID.
* Once  <!-- PH element: phrases/primetime-sdk-name --> applies the default rules, the zone-specific rules can further change the creative priorities based on the `host` (domain) matches on the creative selected by the `default` rules.
* In the included sample rules file with additional zone rules, once  <!-- PH element: phrases/primetime-sdk-name --> applies the `default` rules, if the M3U8 creative domain does not contain `my.domain.com` or `a.bcd.com` and the ad zone is `1234`, the creatives are re-ordered and the Flash VPAID creative is played first if available. Otherwise an MP4 ad is played, and so on down to JavaScript.
* If an ad creative is selected that  <!-- PH element: phrases/primetime-sdk-name --> cannot play natively ( `.mp4`, `.flv`, etc.),  <!-- PH element: phrases/primetime-sdk-name --> issues a repackaging request.
Note that the ad types that can be handled by  <!-- PH element: phrases/primetime-sdk-name --> are still defined through the `validMimeTypes` setting in `AuditudeSettings`.<!-- In Android 2.5 API docs, I see a 
<span class="codeph">setValidMimeTypes</span> but not a 
<span class="codeph">getValidMimeTypes</span>. -->
