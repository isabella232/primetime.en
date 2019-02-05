---
seo-title: Global server configuration data
title: Global server configuration data
uuid: f6d6cb01-2645-4cd2-83ec-0272323a67cd
---

# Global server configuration data{#global-server-configuration-data}

In addition to configuration used by the license server, `HandlerConfiguration` stores configuration information that can be sent to the client to control how licenses are enforced. This is done by creating a `ServerConfigData` class and calling `HandlerConfiguration.setServerConfigData()` (these settings apply only to licenses issued by this license server). The clock windback tolerance is one property that can be set by the license server to control how the client enforces licenses. By default, users may set their machine clock back 4 hours without invalidating licenses. If a license server operator wishes to use a different setting, the new value can be set in the `ServerConfigData` class. When you change the value of any of these settings, be sure to increment the version number by calling `setVersion()`. The new values will only be sent to the client if the version on the client is less than the current `ServerConfigData` version. 
