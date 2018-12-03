---
description: An opportunity generator identifies placement opportunities by custom tags in a stream, ad signaling mode custom markers, and so on. The opportunity generator sends these placement opportunities to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity's properties and metadata.
seo-description: An opportunity generator identifies placement opportunities by custom tags in a stream, ad signaling mode custom markers, and so on. The opportunity generator sends these placement opportunities to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity's properties and metadata.
seo-title: Customize opportunity generators and content resolvers
title: Customize opportunity generators and content resolvers
uuid: 3389c3f2-27a4-44fb-a42d-1bcf9a5da562
index: y
internal: n
snippet: y
---

# Customize opportunity generators and content resolvers{#customize-opportunity-generators-and-content-resolvers}

An opportunity generator identifies placement opportunities by custom tags in a stream, ad signaling mode custom markers, and so on. The opportunity generator sends these placement opportunities to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity's properties and metadata.

 TVSDK includes the following default opportunity generators:

* `ManifestCuesOpportunityGenerator` generates opportunities from the default ad cues ( `#EXT-X-CUE`). 

* `AdSignalingModeOpportunityGenerator` generates an initial opportunity for the specified ad signaling mode. This ignores any cues or timed metadata information. 
* `CustomMarkerOpportunityGenerator` generates opportunities to replace baked-in C3 ads. 
* `AuditudeResolver`’s opportunity generator produces opportunities when lazy ad resolving is on.

TVSDK also includes default content resolvers:

* `CustomRangeResolver` 
* `JSONResolver` 
* `AuditudeResolver`, which can communicate with Primetime ad decisioning.

You can override the default opportunity generators and content resolvers to customize the advertising workflow in ways such as the following:

* Recognize custom tags for ad insertion

  For more information, see  content_resolver . 
* Create a customized ad provider. 
* Black out content.

