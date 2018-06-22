---
description: An opportunity detector is a component that detects custom tags in a stream and identifies placement opportunities. These opportunities are sent to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity properties and metadata.
seo-description: An opportunity detector is a component that detects custom tags in a stream and identifies placement opportunities. These opportunities are sent to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity properties and metadata.
seo-title: Customize opportunity detectors and content resolvers
title: Customize opportunity detectors and content resolvers
---

# Customize opportunity detectors and content resolvers

includes :
* `codeph SpliceOutPlacementOpportunityDetector`, which understands default ad cues

also includes default content resolvers that provide content to be inserted based on the metadata key in the player item:
* `codeph AuditudeResolver` for `codeph AUDITUDE_METADATA_KEY`, which is capable of communicating with  (previously known as ) servers and returning ad breaks to be placed.
* `codeph MetadataResolver` for `codeph JSON_METADATA_KEY`
* `codeph CustomAdMarkersContentResolver` for `codeph TIME_RANGES_METADATA_KEY`

You can override the default opportunity detectors and content resolvers to customize the advertising workflow in the following ways:
* Add support for custom tag detection
* Recognize custom tags for ad insertion
* Create a customized ad provider
* Black out content

