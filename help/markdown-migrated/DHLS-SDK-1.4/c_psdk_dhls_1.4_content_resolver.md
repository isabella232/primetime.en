---
description: An opportunity detector is a component that detects custom tags in a stream and identifies placement opportunities. These opportunities are sent to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity properties and metadata.
seo-description: An opportunity detector is a component that detects custom tags in a stream and identifies placement opportunities. These opportunities are sent to the content resolver, which customizes the content/ad insertion workflow based on the placement opportunity properties and metadata.
seo-title: Customize opportunity detectors and content resolvers
title: Customize opportunity detectors and content resolvers
---

# Customize opportunity detectors and content resolvers

includes default opportunity detectors:
* `codeph SpliceOutOpportunityDetector`, which understands default ad cues
* `codeph AdSignalingModeOpportunityGenerator`, which is responsible for creating initial ad placement opportunities based on the ad signaling mode
* `codeph SpliceOutOpportunityGenerator`, which is responsible for creating ad placement opportunities from any #EXT-X-CUE tag

also includes a default content resolver that provides content to be inserted based on the metadata key in the player item:
* `codeph AuditudeResolver`, capable of communicating with  (previously known as ) servers and returning ad breaks to be placed.

You can override the default opportunity detectors and content resolvers to customize the advertising workflow in the following ways:
* Add support for custom tag detection
* Recognize custom tags for ad insertion
* Create a customized ad provider
* Black out content

