---
description: The ad timeline appropriate to one playing of VOD content may be inappropriate for subsequent plays. You can replace a VOD timeline without changing the content.
seo-description: The ad timeline appropriate to one playing of VOD content may be inappropriate for subsequent plays. You can replace a VOD timeline without changing the content.
seo-title: Replacing VOD timelines
title: Replacing VOD timelines
uuid: ac28f904-8668-4c1a-958c-000dce88db7b
index: y
internal: n
snippet: y
translate: y
---

# Replacing VOD timelines

The ad timeline appropriate to one playing of VOD content may be inappropriate for subsequent plays. You can replace a VOD timeline without changing the content.

Situations in which you might wish to replace a VOD timeline include:

* Replace local ads, but leave national ads during a C3 window.
* Replace burnt-in ads after the C3 window closes.
* Dynamically replace old C3 ads with newer ads of greater duration.
* Insert fewer ads or none at all.


You can replace the ad timeline by submitting a new ad insertion request with the original M3U8 file and a different value of the `pttimeline` query parameter. 
