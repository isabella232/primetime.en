---
seo-title: License caching duration
title: License caching duration
uuid: d448aa43-8cba-4b1d-8609-0dba4bb67042
index: y
internal: n
snippet: y
---

# License caching duration{#license-caching-duration}

The license caching duration specifies how long a license can be cached on disk in the client's local License Store without requiring reacquisition from the license server. Alternatively, you can specify an absolute date and time after which a license can no longer be cached.

Once the cache expiration date has passed, the license is no longer valid, and the client must request a new license from the license server.

Example use case: Use the license caching duration to specify a fixed amount of time valid for a particular license, such as in a rental use case. You can specify a 30-day rental (with license caching) to indicate the total license duration within which to consume the content. 
