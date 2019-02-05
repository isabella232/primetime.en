---
seo-title: Using the DRMManager class overview
title: Using the DRMManager class overview
uuid: 71ce061b-75b6-4ab5-8bbd-cafe7c3e4592
---

# Using the DRMManager class overview{#using-the-drmmanager-class-overview}

Use the `DRMManager` class to manage licenses and Primetime DRM license server sessions in applications.

## License management {#section_8A6F7A2F318B4A62B596AD25A61D991B}

Whenever a device plays protected content, the runtime obtains and caches the license required to view the content. If the application saves the content locally, and the license allows offline playback, the user can view the content in the application without a network connection. Using the `DRMManager`, you can pre-cache the license. The application does not have to obtain the license necessary to view the content. For example, your application could download the media file and then obtain the license while the user is still online.

To preload a license, use a `DRMContentData` object. The `DRMContentData` object contains the URL of the Primetime DRM license server that can provide the license and describes whether user authentication is required. With this information, you can call the `DRMManager` `loadVoucher()` method to obtain and cache the license. The workflow for pre-loading licenses is described in more detail in *Pre-loading licenses for offline playback*.

## Session management {#section_3F0309A5095C4F6586AAC4010BE783AF}

You can also use the `DRMManager` to authenticate the user to a Primetime DRM license server and to manage persistent sessions. Call the `DRMManager` `authenticate()` method to establish a session with the Primetime DRM license server. When authentication is completed successfully, the `DRMManager` dispatches a `DRMAuthenticationCompleteEvent` object. This object contains a session token. You can save this token to establish future sessions so that the user does not have to provide their account credentials. Pass the token to the `setAuthenticationToken()` method to establish a new authenticated session. (The settings of the server that generated the token determine the token expiration and other attributes). 
