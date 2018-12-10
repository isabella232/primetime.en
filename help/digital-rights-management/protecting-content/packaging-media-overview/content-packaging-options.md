---
seo-title: Packaging Options
title: Packaging Options
uuid: 0b764dc2-5d72-4773-a499-d79069d445be
index: y
internal: n
snippet: y
---

# Packaging Options{#packaging-options}

There are numerous options available to you for packaging content. You can specify the options in the `DRMParameters` interface and implement the classes that can interface. With these classes you can set signature and key parameters, as well as indicate whether to encrypt audio content, video content, or script data. To see how these are implemented in the reference implementation, see the descriptions of the Media Packager command line options discussed in *Using the Adobe Primetime DRM Reference Implementations*. These options are based on the Java API, and thus are available for programmatic usage.

The packaging options include:

* Encryption options (audio, video, partial encryption). 
* License server URL that the client uses as the base URL for all requests being sent to the license server 
* License server transport certificate 
* License sever certificate, used to encrypt the CEK 
* Packager credential for signing metadata

