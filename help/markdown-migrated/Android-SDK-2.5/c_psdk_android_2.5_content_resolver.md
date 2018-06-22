---
description: An opportunity generator identifies placement opportunities by custom tags in a stream, ad signaling mode custom markers, and so on. The opportunity generator sends these placement opportunities to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity's properties and metadata.
seo-description: An opportunity generator identifies placement opportunities by custom tags in a stream, ad signaling mode custom markers, and so on. The opportunity generator sends these placement opportunities to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity's properties and metadata.
seo-title: Customize opportunity generators and content resolvers
title: Customize opportunity generators and content resolvers
---

# Customize opportunity generators and content resolvers

includes the following default opportunity generators:
* `codeph ManifestCuesOpportunityGenerator` generates opportunities from the default ad cues (`codeph #EXT-X-CUE`).
* `codeph AdSignalingModeOpportunityGenerator` generates an initial opportunity for the specified ad signaling mode. This ignores any cues or timed metadata information.
* `codeph CustomMarkerOpportunityGenerator` generates opportunities to replace baked-in C3 ads.
* `codeph AuditudeResolver`’s opportunity generator produces opportunities when lazy ad resolving is on.

also includes default content resolvers:
* `codeph CustomRangeResolver`
* `codeph JSONResolver`
* `codeph AuditudeResolver`, which can communicate with .

You can override the default opportunity generators and content resolvers to customize the advertising workflow in ways such as the following:
* Recognize custom tags for ad insertion
  For more information, see []().
  
  
* Create a customized ad provider.
* Black out content.

