---
seo-title: Handling synchronization requests
title: Handling synchronization requests
uuid: 37b2db09-4c09-4216-874b-b570a84569b6
---

# Handling synchronization requests{#handling-synchronization-requests}

. If a license specifies synchronization requirements ( [Requirements for Synchronization,](../../aaxs-protecting-content/content-introduction/content-usage-rules/requirements-for-synchronization.md)) the client will periodically send synchronization requests to the server, based on the frequency specified in the license. To enable synchronization messages, set SyncFrequencyRequirements in a PlayRight.

* The request handler class is `com.adobe.flashaccess.sdk.protocol.sync.SynchronizationHandler` 
* The request message class is `com.adobe.flashaccess.sdk.protocol.sync.SynchronizationRequestMessage` 
* If both the client and server support protocol version 5, the request URL is "License Server URL in metadata: + "/flashaccess/sync/v4". Otherwise, the request URL is “License Server URL in metadata” + “/flashaccess/sync/v3”

Synchronization messages are used to synchronize the client’s time with the server’s time. If licenses are embedded in the content and do not need to be retrieved from a license server, synchronizing the client’s time is important to prevent the client from modifying its clock in order to bypass the license expiration.

Synchronization messages can also be used to communicate the client state information to the server ( `getClientState()`) for rollback detection. See [Rollback Protection](../../aaxs-protecting-content/content-implementing-the-license-server/content-processing-aaxs-requests/content-rollback-detection.md). 
