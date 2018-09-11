---
description: TVSDK contacts an ad delivery service, such as Adobe Primetime ad decisioning, and attempts to obtain the primary playlist file that corresponds to the video stream for the ad. During the ad-resolving phase, TVSDK makes an HTTP call to the remote ad-delivery server and parses the server's response.
seo-description: TVSDK contacts an ad delivery service, such as Adobe Primetime ad decisioning, and attempts to obtain the primary playlist file that corresponds to the video stream for the ad. During the ad-resolving phase, TVSDK makes an HTTP call to the remote ad-delivery server and parses the server's response.
seo-title: Ad-resolving phase
title: Ad-resolving phase
uuid: fe276042-cb13-4eed-b81c-550afb6869da
index: y
internal: n
snippet: y
translate: y
---

# Ad-resolving phase

TVSDK contacts an ad delivery service, such as Adobe Primetime ad decisioning, and attempts to obtain the primary playlist file that corresponds to the video stream for the ad. During the ad-resolving phase, TVSDK makes an HTTP call to the remote ad-delivery server and parses the server's response.

TVSDK supports the following types of ad providers: 
* Metadata ad provider The ad data is encoded in plain-text JSON files. 

* Primetime ad decisioning ad provider TVSDK sends a request, including a set of targeting parameters and an asset identification number, to the Primetime ad decisioningback-end server. Primetime ad decisioningresponds with a synchronized multimedia integration language (SMIL) document that contains the required ad information. 

* Custom ad markers provider Handles the situation where ads are burned into the stream, from the server side. TVSDK does not perform the actual ad insertion, but it needs to keep track of the ads that were inserted on the server side. This provider sets the ad markers that TVSDK uses to perform the ad tracking. 





One of the following failover situations can occur during this phase: 
* The data cannot be retrieved because, for example, of the lack of connectivity or a server-side error, such as a resource cannot be found, and so on.* The data was retrieved, but the format is invalid. This might occur because, for example, the parsing of the inbound data failed. 





TVSDK issues a warning notification about the error and continues processing. 
