---
seo-title: Replay protection
title: Replay protection
uuid: c737998a-9c33-48b4-b741-91106697d71f
index: y
internal: n
snippet: y
---

# Replay protection{#replay-protection}

For replay protection, you may want to check whether the message identifier has been seen recently by calling `RequestMessageBase.getMessageId()`. If so, an attacker may be trying to replay the request, which should be denied. To detect replay attempts, the server can store a list of recently seen message ids and check each incoming request against the cached list. To limit the amount of time the message identifiers need to be stored, call `HandlerConfiguration.setTimestampTolerance()`. If this property is set, the SDK then denies any request that carries a timestamp for more than the specified number of seconds off the server time. 
