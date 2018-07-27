---
description: provides default opportunity generators and content resolvers that place ads in the timeline, and these generators and resolvers are based on nonstandard tags in the manifest. Your application might need to alter the timeline based on opportunities that are identified in the manifest, such as indicators for a blackout period.
seo-description: provides default opportunity generators and content resolvers that place ads in the timeline, and these generators and resolvers are based on nonstandard tags in the manifest. Your application might need to alter the timeline based on opportunities that are identified in the manifest, such as indicators for a blackout period.
seo-title: Opportunity generators and content resolvers
title: Opportunity generators and content resolvers
uuid: 89dff95b-bf67-4f00-99a4-f1bef8e1c330
index: n
internal: n
snippet: y
translate: y
---

# Opportunity generators and content resolvers

An * `opportunity` * represents a point of interest on the timeline that usually indicates an ad placement opportunity. This opportunity can also indicate a custom operation that might affect the timeline, such as a blackout period. An * `opportunity generator` * identifies specific opportunities (tags) in the timeline and notifies  <!-- PH element: phrases/primetime-sdk-name --> that these opportunities have been tagged. Opportunities are identified in a timeline in `TimedMetadata`. The `SpliceOutOpportunityGenerator` creates opportunities based on the `TimedMetadata` objects that are created for each ad tag that has been detected in the manifest, and the `AdSignalingModeOpportunityGenerator` creates the initial opportunity that is based on the `MediaPlayerItem` type and its associated ad signaling mode. 
When your application is notified about an opportunity (tag), your application might alter the timeline by, for example, inserting a series of ads, by switching to an alternate stream (blackouts) or by otherwise editing the timeline content. By default,  <!-- PH element: phrases/primetime-sdk-name --> calls the appropriate * `content resolver` * to implement the required timeline changes or actions. Your application can use the default  <!-- PH element: phrases/primetime-sdk-name --> advertisement content resolver or register its own content resolver.
You can also use `PSDKConfig.adTags` to add more ad marker tags/cues for the default `SpliceOutOpportunityGenerator` class and use `PSDKConfig.setSubscribedTags` so that  <!-- PH element: phrases/primetime-sdk-name --> can notify your application about additional tags that might have advertising workflow information.
One possible use of a custom resolver is for blackout periods. To handle these periods, your application could implement and register a blackout opportunity detector that is responsible for handling blackout tags. When  <!-- PH element: phrases/primetime-sdk-name --> encounters this tag, it polls all the registered content resolvers to find the first one that handles the specified tag. In this example, it is the blackout content resolver, which can, for example, replace the current item with alternate content on the player for the duration that is specified by the tag.
