---
seo-title: License caching duration
title: License caching duration
uuid: 6379f39e-6dcf-4c2b-9fbb-50a542eff10f
index: y
internal: n
snippet: y
---

# License caching duration{#license-caching-duration}

The license caching duration specifies how long a license can be cached on disk in the client's local License Store without requiring reacquisition from the license server. Alternatively, you can specify an absolute date and time after which a license can no longer be cached.

Once the cache expiration date has passed, the license is no longer valid, and the client must request a new license from the license server.

Example use case: Use the license caching duration to specify a fixed amount of time valid for a particular license, such as in a rental use case. You can specify a 30-day rental (with license caching) to indicate the total license duration within which to consume the content. 
