---
description: Replay protection prevents an attacker from replaying a license request message and potentially causing a denial-of-service (DoS) attack against the client.
seo-description: Replay protection prevents an attacker from replaying a license request message and potentially causing a denial-of-service (DoS) attack against the client.
seo-title: Replay protection
title: Replay protection
uuid: f38cf3f7-89e8-4c9d-96d8-53364d3c9bee
index: y
internal: n
snippet: y
---

# Replay protection{#replay-protection}

Replay protection prevents an attacker from replaying a license request message and potentially causing a denial-of-service (DoS) attack against the client.

A DoS attack is an attempt by attackers to prevent legitimate users of a service from using that service. For example, a replay attack that uses the rollback counter could be used to “trick” the License Server into thinking that the DRM client has rolled back its state, which causes a suspension of the account.

To learn more about replay protection, see [ `AbstractRequestMessage.getMessageId()`](http://help.adobe.com/en_US/primetime/api/drm-apis/server/javadocs-flashaccess-pro/com/adobe/flashaccess/sdk/protocol/AbstractRequestMessage.html#getMessageId()). 
