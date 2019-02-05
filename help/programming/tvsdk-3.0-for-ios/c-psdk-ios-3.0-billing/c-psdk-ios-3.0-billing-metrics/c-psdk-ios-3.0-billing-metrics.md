---
description: To accommodate customers who want to pay only for what they use, rather than a fixed rate regardless of actual use, Adobe collects usage metrics and uses these metrics to determine how much to bill the customers.
seo-description: To accommodate customers who want to pay only for what they use, rather than a fixed rate regardless of actual use, Adobe collects usage metrics and uses these metrics to determine how much to bill the customers.
seo-title: Billing usage metrics
title: Billing usage metrics
uuid: e792cc72-b1ae-42ce-8b71-f9f9f1de0614
---

# Billing usage metrics{#billing-usage-metrics}

To accommodate customers who want to pay only for what they use, rather than a fixed rate regardless of actual use, Adobe collects usage metrics and uses these metrics to determine how much to bill the customers.

Every time the player generates a stream start event, TVSDK starts to send HTTP messages periodically to Adobe's billing system. The period, known as billable duration, can be different for standard VOD, pro VOD (mid-roll ads enabled), and live content. The default duration for each content type is 30 minutes, but your contract with Adobe determines the actual values.

The messages contain the following information:

* Content type (live, linear, or VOD) 
* Content URL 
* Whether ads are enabled 
* Whether mid-roll ads are enabled (VOD only) 
* Whether the stream is protected by DRM 
* The TVSDK version and platform

Adobe pre-configures this arrangement, but if you want to change the arrangement, work with your Adobe Enablement representative.

To monitor the statistics that TVSDK sends to Adobe, obtain the URL from your Adobe Enablement representative, and use a network capture tool, for example, Charles, to see the data. 
