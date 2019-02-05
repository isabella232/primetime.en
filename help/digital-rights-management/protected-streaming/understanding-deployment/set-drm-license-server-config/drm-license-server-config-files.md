---
seo-title: License server configuration files
title: License server configuration files
uuid: 7c7e0f76-2ced-45af-9542-99e06ec31cda
---

# License server configuration files{#license-server-configuration-files}

The Adobe Primetime DRM Server for Protected Streaming requires the following types of configuration files:

* Global configuration file ( [!DNL flashaccess-global.xml]) 
* Tenant configuration file for each tenant ( [!DNL flashaccess-tenant.xml])

After you complete editing the configuration files, Adobe recommends that you use the utilities provided with the Primetime DRM Server for Protected Streaming to verify that the files are well-formed.

See *Configuration Validator*.

If you want to avoid making passwords available in clear text in the configuration files, then you must encrypt all passwords that you have specified in the global and tenant configuration files by using the Scrambler tool that Adobe has provided.

See *Password Scrambler* for more information on how to encrypt passwords. 
