---
description: contacts an ad delivery service, such as , and attempts to obtain the primary playlist file that corresponds to the video stream for the ad. During the ad-resolving phase, makes an HTTP call to the remote ad-delivery server and parses the server's response.
seo-description: contacts an ad delivery service, such as , and attempts to obtain the primary playlist file that corresponds to the video stream for the ad. During the ad-resolving phase, makes an HTTP call to the remote ad-delivery server and parses the server's response.
seo-title: Ad-resolving phase
title: Ad-resolving phase
uuid: d1296892-d7ee-4a17-913f-3a153df45a14
index: n
internal: n
snippet: y
translate: y
---

# Ad-resolving phase

 <!-- PH element: phrases/primetime-sdk-name --> supports the following types of ad providers:
* Metadata ad provider The ad data is encoded in plain-text JSON files.

* <!-- PH element: phrases/auditude-name --> ad provider <!-- PH element: phrases/primetime-sdk-name --> sends a request, including a set of targeting parameters and an asset identification number, to the <!-- PH element: phrases/auditude-name --> back-end server. <!-- PH element: phrases/auditude-name --> responds with a SMIL (synchronized multimedia integration language) document that contains the required ad information.


One of the following failover situations can occur during this phase: 
* The data cannot be retrieved for reasons including a lack of connectivity or a server-side error, such as a resource cannot be found and so on.
* The data was retrieved, but the format is invalid. This might occur because, for example, the parsing of the inbound data failed.


<!-- PH element: phrases/primetime-sdk-name --> issues a warning notification about the error and continues processing.
