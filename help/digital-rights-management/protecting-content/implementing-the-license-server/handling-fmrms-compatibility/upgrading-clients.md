---
description: There are two types of requests related to Flash Media Rights Management Server 1.x compatibility. One type of request is used to prompt 1.x clients to upgrade to a runtime that supports Adobe Primetime DRM 2.0 or later. Another is used to update 1.x metadata to the Primetime DRM format before a license can be requested. Support for these requests is only needed if you previously deployed any content that uses FMRMS 1.0 or 1.5.
seo-description: There are two types of requests related to Flash Media Rights Management Server 1.x compatibility. One type of request is used to prompt 1.x clients to upgrade to a runtime that supports Adobe Primetime DRM 2.0 or later. Another is used to update 1.x metadata to the Primetime DRM format before a license can be requested. Support for these requests is only needed if you previously deployed any content that uses FMRMS 1.0 or 1.5.
seo-title: Upgrading clients
title: Upgrading clients
uuid: c32ee087-2edf-4d11-be36-e2b31f3769de
index: y
internal: n
snippet: y
---

# Upgrading clients{#upgrading-clients}

There are two types of requests related to Flash Media Rights Management Server 1.x compatibility. One type of request is used to prompt 1.x clients to upgrade to a runtime that supports Adobe Primetime DRM 2.0 or later. Another is used to update 1.x metadata to the Primetime DRM format before a license can be requested. Support for these requests is only needed if you previously deployed any content that uses FMRMS 1.0 or 1.5.

If an FMRMS 1.x client contacts a Adobe Primetime DRM server, the server needs to prompt the client to upgrade.

* The request handler class is `com.adobe.flashaccess.sdk.protocol.compatibility.FMRMSv1RequestHandler`. 
* The request URL is "*Base URL from 1.x content*" + " [!DNL /edcws/services/urn:EDCLicenseService]"

  Unlike other Adobe Primetime request handlers, this handler does not provide access to any request information or require any response data to be set. Create an instance of the `FMRMSv1RequestHandler`, and then call `close()`

