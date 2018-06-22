---
description: 
keywords: creative selection rules;AdobeTVSDKConfig
seo-description: 
seo-title: Applying creative selection rules
title: Applying creative selection rules
---

# Applying creative selection rules

TVSDK applies creative selection rules in the following ways:

* applies all `codeph default` rules first, followed by the zone-specific rules.
* ignores any rules that are not defined for the current zone ID.
* Once  applies the default rules, the zone-specific rules can further change the creative priorities based on the `codeph host` (domain) matches on the creative selected by the `codeph default` rules.
* In the included sample rules file with additional zone rules, once  applies the `codeph default` rules, if the M3U8 creative domain does not contain `filepath my.domain.com` or `filepath a.bcd.com` and the ad zone is `codeph 1234`, the creatives are re-ordered and the Flash VPAID creative is played first if available. Otherwise an MP4 ad is played, and so on down to JavaScript.
* If an ad creative is selected that  cannot play natively (`filepath .mp4`, `filepath .flv`, etc.),  issues a repackaging request.
Note that the ad types that can be handled by  are still defined through the `codeph validMimeTypes` setting in `codeph AuditudeSettings`.

