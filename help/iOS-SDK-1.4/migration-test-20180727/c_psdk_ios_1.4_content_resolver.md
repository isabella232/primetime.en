---
description: An opportunity detector is a component that detects custom tags in a stream and identifies placement opportunities. These opportunities are sent to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity properties and metadata.
seo-description: An opportunity detector is a component that detects custom tags in a stream and identifies placement opportunities. These opportunities are sent to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity properties and metadata.
seo-title: Customize opportunity detectors and content resolvers
title: Customize opportunity detectors and content resolvers
uuid: 55563e73-3ed6-4258-a353-fb0c533f5ede
index: n
internal: n
snippet: y
translate: y
---

# Customize opportunity detectors and content resolvers

 <!-- PH element: phrases/primetime-sdk-name --> includes a default opportunity detector:
* `PTOpportunityResolver`, which understands default ad cues

<!-- PH element: phrases/primetime-sdk-name --> also includes a default content resolver that provides content to be inserted based on the metadata key in the player item:
* `PTContentResolver`

You can override the default opportunity detectors and content resolvers to customize the advertising workflow in the following ways: 
* Add support for custom tag detection
* Recognize custom tags for ad insertion
* Create a customized ad provider
* Black out content

