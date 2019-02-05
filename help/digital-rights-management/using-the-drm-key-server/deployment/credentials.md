---
seo-title: Primetime DRM credentials
title: Primetime DRM credentials
uuid: 0bff9ad2-31ee-485c-bb32-5e9a33bf0c87
---

# Primetime DRM credentials{#primetime-drm-credentials}

To process key requests from Primetime DRM iOS and Xbox 360 clients, the Primetime DRM Key Server must be configured with a set of credentials issued by Adobe. These credentials can either be stored in PKCS#12 ( [!DNL .pfx]) files or on an HSM.

The [!DNL .pfx] files can be located anywhere, but for ease of configuration, Adobe recommends placing the [!DNL .pfx] files in the tenant’s configuration directory. For more information, see [Key Server configuration files.](../../using-the-drm-key-server/deployment/configuration-files.md).

## HSM configuration {#section_13A19E3E32934C5FA00AEF621F369877}

If you choose to use an HSM to store your server credentials, you must load the private keys and certificates onto the HSM and create a *pkcs11.cfg* configuration file. This file must be located in the *KeyServer.ConfigRoot* directory. See the [!DNL <Primetime DRM Key Server>/configs] directory for an example PKCS 11 configuration file. For information on the format of [!DNL pkcs11.cfg], see the Sun PKCS11 provider documentation.

To verify that your HSM and Sun PKCS11 configuration files are configured properly, you can use the following command from the directory where the [!DNL pkcs11.cfg] file is located ( [!DNL keytool] is installed with the Java JRE and JDK): 

```
keytool -keystore NONE -storetype PKCS11 -providerClass sun.security.pkcs11.SunPKCS11 
  -providerArg pkcs11.cfg -list
```

If you see your credentials in the list, the HSM is configured properly and the Key Server will be able to access the credentials. 
