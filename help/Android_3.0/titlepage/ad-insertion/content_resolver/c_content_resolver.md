---
description: An opportunity generator identifies placement opportunities by custom tags in a stream, ad signaling mode custom markers, and so on. The opportunity generator sends these placement opportunities to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity's properties and metadata.
seo-description: An opportunity generator identifies placement opportunities by custom tags in a stream, ad signaling mode custom markers, and so on. The opportunity generator sends these placement opportunities to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity's properties and metadata.
seo-title: Customize opportunity generators and content resolvers
title: Customize opportunity generators and content resolvers
uuid: eb70224e-9d46-4f2b-8f64-23b67d72533c
index: y
internal: n
snippet: y
translate: y
---

# Customize opportunity generators and content resolvers

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
* Recognize custom tags for ad insertion For more information, see  content_resolver . 

* Create a customized ad provider.
* Black out content.



