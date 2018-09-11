---
description: Most advertisers require some detailed information about when, for how long, and how successfully their ads were viewed. The most efficient approach is to have the client player send reports as it plays the ads, but the manifest server also supports server-side and hybrid ad tracking.
seo-description: Most advertisers require some detailed information about when, for how long, and how successfully their ads were viewed. The most efficient approach is to have the client player send reports as it plays the ads, but the manifest server also supports server-side and hybrid ad tracking.
seo-title: Ad tracking
title: Ad tracking
uuid: 02b5576d-5027-4ca7-b262-b5b06e8b6d7b
index: y
internal: n
snippet: y
translate: y
---

# Ad tracking

Most advertisers require some detailed information about when, for how long, and how successfully their ads were viewed. The most efficient approach is to have the client player send reports as it plays the ads, but the manifest server also supports server-side and hybrid ad tracking.

When enabling ad tracking the client specifies one of the following approaches: 

* ** Client side ** Along with the ad-stitched playlist, the server sends the client a JSON, VMAP, or in-manifest structure specifying tracking events and URLs. This method is Interactive Advertising Bureau (IAB) compliant 

* ** Server side ** The client does not participate in ad tracking. The server sends whatever ad tracking information it can. Tracking data is calculated only on the server side and may not match with client side playback activity. For example, if an end-user does not view the entire ad, after the segments are delivered, the server still considers the ad to be played. 

* ** Hybrid ** This is like client-side tracking, but the client sends its reports to the manifest server, which relays them to the appropriate URLs. Advertisers receive the same information as with client side tracking. This mode accommodates clients running with restricted internet access. 



