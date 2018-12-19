---
seo-title: Global configuration file
title: Global configuration file
uuid: 24772316-4719-49ff-aa13-37ff5da3d036
index: y
internal: n
snippet: y
---

# Global configuration file{#global-configuration-file}

The [!DNL flashaccess-keyserver-global.xml] configuration file contains settings that apply to all tenants of the Key Server. This file must be located in `KeyServer.ConfigRoot`. See the [!DNL configs] directory for an example global configuration file. The global configuration file includes the following:

* Logging - Specifies the logging level and how frequently log files are rolled. 
* HSM password - Required only if an HSM is used to store server credentials.

See the comments in the example global configuration file located in [!DNL <Primetime DRM Key Server>/configs] for more details. 
