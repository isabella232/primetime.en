---
description: An opportunity detector is a component that detects custom tags in a stream and identifies placement opportunities. These opportunities are sent to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity properties and metadata.
seo-description: An opportunity detector is a component that detects custom tags in a stream and identifies placement opportunities. These opportunities are sent to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity properties and metadata.
seo-title: Customize opportunity detectors and content resolvers
title: Customize opportunity detectors and content resolvers
uuid: eed64944-d049-4c2f-8491-8466c36260e3
index: n
internal: n
snippet: y
translate: y
---

# Customize opportunity detectors and content resolvers

 <!-- PH element: phrases/primetime-sdk-name --> includes: 
* `SpliceOutPlacementOpportunityDetector`, which understands default ad cues

<!-- PH element: phrases/primetime-sdk-name --> also includes default content resolvers that provide content to be inserted based on the metadata key in the player item:
* `AuditudeResolver` for `AUDITUDE_METADATA_KEY`, which is capable of communicating with  <!-- PH element: phrases/auditude-name-long --> (previously known as <!-- PH element: phrases/auditude-name-previously-known-as --> ) servers and returning ad breaks to be placed.
* `MetadataResolver` for `JSON_METADATA_KEY`
* `CustomAdMarkersContentResolver` for `TIME_RANGES_METADATA_KEY`

You can override the default opportunity detectors and content resolvers to customize the advertising workflow in the following ways: 
* Add support for custom tag detection
* Recognize custom tags for ad insertion
* Create a customized ad provider
* Black out content

