---
description: To accommodate customers who want to pay only for what they use, rather than a fixed rate regardless of actual use, Adobe collects usage metrics and uses these metrics to determine how much to bill the customers.
seo-description: To accommodate customers who want to pay only for what they use, rather than a fixed rate regardless of actual use, Adobe collects usage metrics and uses these metrics to determine how much to bill the customers.
seo-title: Billing metrics
title: Billing metrics
uuid: 02a2e071-34c3-4e32-845d-beb1323ef8ce
index: n
internal: n
snippet: y
translate: y
---

# Billing metrics

Every time the player generates a stream start event,  <!-- PH element: phrases/primetime-sdk-name --> starts to send HTTP messages periodically to Adobe's billing system. The period, known as billable duration, can be different for standard VOD, pro VOD (mid-roll ads enabled), and live content. The default duration for each content type is 30 minutes, but your contract with Adobe determines the actual values.
The messages contain the following information: 
* Content type (live, linear, or VOD)
* Content URL
* Whether ads are enabled
* Whether mid-roll ads are enabled (VOD only)
* Whether the stream is protected by DRM
* The  <!-- PH element: phrases/primetime-sdk-name --> version and platform
Adobe pre-configures this arrangement, but if you want to change the arrangement, work with your Adobe Enablement representative.
To monitor the statistics that  <!-- PH element: phrases/primetime-sdk-name --> sends to Adobe, obtain the URL from your Adobe Enablement representative, and use a network capture tool, for example, Charles, to see the data.
