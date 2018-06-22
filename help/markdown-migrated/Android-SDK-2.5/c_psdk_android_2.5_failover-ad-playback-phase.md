---
description: downloads the ad segments and renders them on the device's screen.
seo-description: downloads the ad segments and renders them on the device's screen.
seo-title: Ad-playback phase
title: Ad-playback phase
---

# Ad-playback phase

Now,  has resolved ads, positioned the ads on the timeline, and attempts to render the content on the screen.

The following main classes of errors might occur during the following phases:
* When connecting to the host server.
* When downloading the manifest file.
* When downloading the media segments.

forwards the triggered events to your application, including notification events that are triggered when:
* A failover happens.
* The profile is changed because of the failover algorithm.
* All failover options have been considered, and no additional action can be taken automatically.
  Your application needs to take the appropriate action.
  
  

Regardless of whether errors occur,  calls `codeph onAdBreakComplete` for each `codeph onAdBreakStart` and `codeph onAdComplete` for every `codeph onAdStart`. However, if segments could not be downloaded, there might be gaps in the timeline. When the gaps are large enough, the values in the playhead position and the reported ad progress might exhibit discontinuities.

