---
seo-title: Key Server configuration files
title: Key Server configuration files
uuid: def5c1a6-decd-4cb8-9bd8-9c1c81f5a3ae
---

# Key Server configuration files{#key-server-configuration-files}

The Primetime DRM Key Server requires two types of configuration files:

* A global configuration file, [!DNL flashaccess-keyserver-global.xml] 
* A tenant configuration file for each tenant, [!DNL flashaccess-keyserver-tenant.xml]

If changes are made to the configuration files, the server must be restarted for the changes to take effect.

To avoid making passwords available in clear text in the configuration files, all passwords specified in the global and tenant configuration files must be encrypted. For more information on encrypting passwords, see [*Password Scrambler* in *Using the Primetime DRM Server for Protected Streaming*](../../protected-streaming/understanding-deployment/drm-for-protected-streaming-utilities/password-scrambler.md). 
