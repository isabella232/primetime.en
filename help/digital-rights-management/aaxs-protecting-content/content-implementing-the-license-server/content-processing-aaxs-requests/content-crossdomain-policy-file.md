---
seo-title: Crossdomain policy file
title: Crossdomain policy file
uuid: fc05aa5e-6fbd-445f-a22a-f795d5a0b3ad
index: y
internal: n
snippet: y
---

# Crossdomain policy file {#crossdomain-policy-file}

If the license server is hosted on a different domain than the video playback SWF, then a cross-domain policy file (crossdomain.xml) is necessary to allow the SWF to request licenses from the license server. A cross-domain policy file is an XML file that provides a way for the server to indicate that its data and documents are available to SWF files served from other domains. Any SWF file served from a domain specified in the license server’s cross-domain policy file is permitted to access data or assets from that license server.

Adobe recommends that developers follow best practices when deploying the cross-domain policy file by only allowing trusted domains to access the license server and limiting the access to the license sub-directory on the web server.

For more information on cross-domain policy files, please see the following locations:

* Web site controls (policy files)
* Cross-domain policy file specification: [https://www.adobe.com/devnet/articles/crossdomain_policy_file_spec.html](https://www.adobe.com/devnet/articles/crossdomain_policy_file_spec.html)

