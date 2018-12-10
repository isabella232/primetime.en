---
seo-title: Key Server configuration files
title: Key Server configuration files
uuid: 6847894f-d781-4973-8b0f-e15500fd3063
index: y
internal: n
snippet: y
---

# Key Server configuration files{#key-server-configuration-files}

The Primetime DRM Key Server requires two types of configuration files:

* A global configuration file, [!DNL flashaccess-keyserver-global.xml] 
* A tenant configuration file for each tenant, [!DNL flashaccess-keyserver-tenant.xml]

If changes are made to the configuration files, the server must be restarted for the changes to take effect.

To avoid making passwords available in clear text in the configuration files, all passwords specified in the global and tenant configuration files must be encrypted. For more information on encrypting passwords, see [*Password Scrambler* in *Using the Primetime DRM Server for Protected Streaming*](http://help.adobe.com/en_US/primetime/drm/5.3/protected_streaming/index.html#DRM-concept-Password_scrambler). 
