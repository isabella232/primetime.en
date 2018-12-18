---
description: These classes assist in detecting opportunities in a timeline for placement of content, such as ads.
seo-description: These classes assist in detecting opportunities in a timeline for placement of content, such as ads.
seo-title: Timeline generators classes
title: Timeline generators classes
uuid: 1e36b738-0684-44f0-b3c3-dd656c70f705
index: y
internal: n
snippet: y
---

# Timeline generators classes{#timeline-generators-classes}

These classes assist in detecting opportunities in a timeline for placement of content, such as ads.

 Package: [com.adobe.mediacore.timeline.generators](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/generators/package-detail.html) 

|  Name  | Description  |
|---|---|
| ` [AdSignalingModeOpportunityGenerator](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/generators/AdSignalingModeOpportunityGenerator.html)`  | Class which creates an initial opportunity for the specified advertising signaling mode.  |
| ` [OpportunityGenerator](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/generators/OpportunityGenerator.html)`  | Base class for all opportunity generators.  |
|  ` [OpportunityGeneratorClient](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/generators/OpportunityGeneratorClient.html)`  | Interface used by opportunity generators to communicate with TVSDK components.  |
| ` [SpliceOutOpportunityGenerator](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/generators/SpliceOutOpportunityGenerator.html)`  | Class which monitors the playback timeline and detects ad placement opportunities inserted into the manifest as SpliceOut comments.  |
| ` [TimedMetadataOpportunityGenerator](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/generators/TimedMetadataOpportunityGenerator.html)`  | Default implementation of an opportunity generator which is using timed metadata information to detect and generate advertisement opportunities.  |

