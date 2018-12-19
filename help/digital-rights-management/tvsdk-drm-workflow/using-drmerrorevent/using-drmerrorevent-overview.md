---
seo-title: Using the DRMErrorEvent class overview
title: Using the DRMErrorEvent class overview
uuid: 73da92a5-249e-4d7d-8b43-33ae048fd7d3
index: y
internal: n
snippet: y
---

# Using the DRMErrorEvent class overview{#using-the-drmerrorevent-class-overview}

Primetime dispatches a `DRMErrorEvent` object when a Primetime object, trying to play protected content, encounters a [DRM-related error](http://help.adobe.com/en_US/primetime/drm/index.html#reference-DRM_Client_Error_Messages). If user credentials are invalid, the `DRMAuthenticateEvent` object repeatedly dispatches until the user enters valid credentials or the application denies further attempts. The application is responsible for listening to any other DRM error events to detect, identify, and handle the [DRM-related errors](http://help.adobe.com/en_US/primetime/drm/index.html#reference-DRM_Client_Error_Messages).

Even with valid user credentials, the terms of the content’s license can still prevent a user from viewing the encrypted content. For example, a user can be denied access for attempting to view content in an unauthorized application (e.g., Application Whitelisting). An unauthorized application is one that has not been signed with a whitelisted Application Signing Certificate. In this case, a `DRMErrorEvent` object is dispatched.

Error events can also be fired if the content is corrupted or if the application’s version does not match what the license specifies. The application must provide an appropriate mechanism for handling errors. 