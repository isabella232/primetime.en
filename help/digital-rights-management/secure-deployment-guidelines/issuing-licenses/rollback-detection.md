---
description: If your implementation of Adobe Primetime DRM uses business rules that require the client to maintain state (for example, the playback window interval), Adobe recommends that the server keeps track of the rollback counter and use AIR or SWF whitelisting.
seo-description: If your implementation of Adobe Primetime DRM uses business rules that require the client to maintain state (for example, the playback window interval), Adobe recommends that the server keeps track of the rollback counter and use AIR or SWF whitelisting.
seo-title: Rollback detection
title: Rollback detection
uuid: 7bb432cc-047f-4f85-9393-f6ac9e6338e0
index: y
internal: n
snippet: y
---

# Rollback detection{#rollback-detection}

If your implementation of Adobe Primetime DRM uses business rules that require the client to maintain state (for example, the playback window interval), Adobe recommends that the server keeps track of the rollback counter and use AIR or SWF whitelisting.

The rollback counter is sent to the server in most requests from the client. If your implementation of Primetime DRM does not require the rollback counter, it can be ignored. Otherwise, Adobe recommends that the server store the random machine ID, which is obtained using ` [MachineToken.getUniqueId()](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/cert/MachineId.html#getUniqueId())`, and the current counter value in a database.

For more information on how to increment and track the rollback counter, see [ `ClientState`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/protocol/ClientState.html) and [Rollback detection](http://help.adobe.com/en_US/primetime/drm/5.3/protecting_content/index.html#DRM-concept-Rollback_detection). 
