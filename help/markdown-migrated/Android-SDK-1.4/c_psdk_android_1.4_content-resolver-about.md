---
description: provides default opportunity generators and content resolvers that place ads in the timeline, and these generators and resolvers are based on nonstandard tags in the manifest. Your application might need to alter the timeline based on opportunities that are identified in the manifest, such as indicators for a blackout period.
seo-description: provides default opportunity generators and content resolvers that place ads in the timeline, and these generators and resolvers are based on nonstandard tags in the manifest. Your application might need to alter the timeline based on opportunities that are identified in the manifest, such as indicators for a blackout period.
seo-title: Opportunity generators and content resolvers
title: Opportunity generators and content resolvers
---

# Opportunity generators and content resolvers

An `term opportunity` represents a point of interest on the timeline that usually indicates an ad placement opportunity. This opportunity can also indicate a custom operation that might affect the timeline, such as a blackout period. An `term opportunity generator` identifies specific opportunities (tags) in the timeline and notifies  that these opportunities have been tagged. Opportunities are identified in a timeline in by including a nonstandard (non-HLS) tag.

When your application is notified about an opportunity (tag), your application might alter the timeline by, for example, inserting a series of ads, by switching to an alternate stream (blackouts) or by otherwise editing the timeline content. By default,  calls the appropriate `term content resolver` to implement the required timeline changes or actions. Your application can use the default  advertisement content resolver or register its own content resolver.

You can also use  to add more ad marker tags/cues so that  can recognize and use `codeph MediaPlayerItemConfig.subscribedTags` and notify your application about additional tags that might have advertising workflow information.

One possible use of a custom resolver is for blackout periods. To handle these periods, your application could implement and register a blackout opportunity detector that is responsible for handling blackout tags. When  encounters this tag, it polls all the registered content resolvers to find the first one that handles the specified tag. In this example, it is the blackout content resolver, which can, for example, replace the current item with alternate content on the player for the duration that is specified by the tag.

