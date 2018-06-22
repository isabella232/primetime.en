---
description: contacts an ad delivery service, such as , and attempts to obtain the primary playlist file that corresponds to the video stream for the ad. During the ad-resolving phase, makes an HTTP call to the remote ad-delivery server and parses the server's response.
seo-description: contacts an ad delivery service, such as , and attempts to obtain the primary playlist file that corresponds to the video stream for the ad. During the ad-resolving phase, makes an HTTP call to the remote ad-delivery server and parses the server's response.
seo-title: Ad-resolving phase
title: Ad-resolving phase
---

# Ad-resolving phase

supports the following types of ad providers:
* Metadata ad provider
  The ad data is encoded in plain-text JSON files.
  
  
* ad provider
  sends a request, including a set of targeting parameters and an asset identification number, to the  back-end server.  responds with a SMIL (synchronized multimedia integration language) document that contains the required ad information.
  
  
* Custom ad markers provider
  Handles the situation where ads are burned into the stream, from the server side.  does not perform the actual ad insertion, but it needs to keep track of the ads that were inserted on the server side. This provider sets the ad markers that  uses to perform the ad tracking.
  
  

One of the following failover situations can occur during this phase:
* The data cannot be retrieved for reasons including a lack of connectivity or a server-side error, such as a resource cannot be found and so on.
* The data was retrieved, but the format is invalid.
  This might occur because, for example, the parsing of the inbound data failed.
  
  

issues a warning notification about the error and continues processing.

