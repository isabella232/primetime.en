---
seo-title: Tenant configuration files
title: Tenant configuration files
uuid: c5d07a52-52a7-4ec3-868d-2011a89488e4
index: y
internal: n
snippet: y
---

# Tenant configuration files{#tenant-configuration-files}

The [!DNL flashaccess-ioskeyserver-tenant.xml] and [!DNL flashaccess-xboxkeyserver-tenant.xml] configuration files contain settings that apply to a specific tenant of the Primetime DRM Key Server. Each tenant has its own instance of these configuration files located in [!DNL <KeyServer.ConfigRoot>/faxsks/tenants/tenantname]. See the [!DNL configs/faxsks/tenants/sampletenant] directory for an example tenant configuration file.

You can specify all file paths in the tenant configuration file as either absolute paths or paths relative to the tenant’s configuration directory ( [!DNL <KeyServer.ConfigRoot>/faxsks/tenants/tenantname]).

All tenant configuration files include:

* Key Server Credentials - Specifies one or more Key Server credentials (certificate and private key) issued by Adobe. Can be specified as a path to a [!DNL .pfx] file and a password, or an alias for a credential stored on an HSM. Several such credentials can be specified here, either as file paths, or key aliases, or both.

The **iOS** tenant configuration file includes:

* Key Delivery Window - (Optional) Specifies key delivery request timestamp validity window (in seconds). Default value is 500 seconds.

The **Xbox 360** tenant configuration file includes:

* XSTS Credential - Specifies the application developer's credential used to decrypt XSTS tokens 
* XSTS Signing Certificate - Specifies the certificate used to verify the signature on XSTS tokens. 
* Packager Whitelist - Packager certificates that are trusted by the Key Server. If there are no packager certificates contained in the list, then all packager certificates will be trusted.

