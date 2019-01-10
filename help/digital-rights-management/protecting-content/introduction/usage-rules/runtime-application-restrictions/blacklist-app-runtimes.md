---
description: null
seo-description: null
seo-title: Blacklist of application runtimes
title: Blacklist of application runtimes
uuid: fc3c9bd6-b1e6-4534-b29c-cd9a35b80928
index: y
internal: n
snippet: y
---

# Blacklist of application runtimes{#blacklist-of-application-runtimes}

Blacklist of application runtimes specifies the version of the Primetime client or Flash Runtime that cannot access content. Specify the restricted runtime (Flash Player, AIR, or iOS), platform, and version.

Example use case: Similar to the Primetime DRM Client blacklist, the latest version of the Flash Player, AIR, or iOS runtimes can be specified as the minimum version required for license acquisition and content playback.

You can identify the application runtime by any of the attributes supported for Primetime DRM client versions, in addition to the following attributes:  

| **Attribute** |**Supported Values** |**Match Criteria** |**Description** |
|---|---|---|---|
|  Application  | `“FlashPlayer”, “AIR”, "DRM_Library", "AVE"`  | Exact Match  | Identifies the name of the application runtime.  |

