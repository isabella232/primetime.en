---
seo-title: Global configuration file
title: Global configuration file
uuid: 10370bc0-36ab-4e43-9e75-c46a7177874c
---

# Global configuration file{#global-configuration-file}

The flashaccess-global.xml configuration file contains settings that apply to all tenants of the license server. This file must be located in *LicenseServer.ConfigRoot*. See the configs directory for an example global configuration file. The global configuration file includes the following:

* Caching — Controls caching of config files in memory. For an explanation of the caching settings, see "Updating configuration files". 
* Logging — Specifies the logging level and how frequently log files are rolled. 
* HSM password — Required only if an HSM is used to store server credentials.

See the comments in the example global configuration file located in `<AdobeAccessDVD>\Adobe Access Server for Protected Streaming\configs` for more details. 
