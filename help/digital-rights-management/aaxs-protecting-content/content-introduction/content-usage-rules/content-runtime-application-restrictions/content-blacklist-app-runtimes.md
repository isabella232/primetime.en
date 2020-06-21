---
seo-title: Block list of application runtimes restricted from accessing protected content
title: Block list of application runtimes restricted from accessing protected content
uuid: 462a2c09-b335-4768-bd0e-1359db169d69
---

# Block list of application runtimes restricted from accessing protected content {#blocklist-of-application-runtimes-restricted-from-accessing-protected-content}

Specifies the version of the Primetime or Flash Runtime that cannot access content. Specify the restricted runtime (Flash Player, AIR, or iOS), platform, and version.

Example use case: Similar to the DRM Client block list, the latest version of the Flash Player, AIR, or iOS runtimes can be specified as the minimum version required for license acquisition and content playback.

The application runtime may be identified by any of the attributes supported for DRM client versions, in addition to the following attributes:  

| **Attribute** |**Supported Values** |**Match Criteria** |**Description** |
|---|---|---|---|
|  Application  | “FlashPlayer”, “AIR”, "DRM_Library", "AVE"  | Exact Match  | Identifies the name of the application runtime.  |

