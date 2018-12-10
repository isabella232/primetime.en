---
seo-title: Java system properties
title: Java system properties
uuid: 32b290bd-e6b4-4e8f-82ee-3d4737c5923e
index: y
internal: n
snippet: y
---

# Java system properties{#java-system-properties}

You have the option to set the following two Java system properties to modify the location of configuration and log files for the Primetime DRM Key Server:

* `KeyServer.ConfigRoot` - This directory contains all of the configuration files for the Primetime DRM Key Server. For details on the contents of these files, see [Key Server configuration files](../../using-the-drm-key-server/deployment/configuration-files.md). If not set, the default is [!DNL CATALINA_BASE/keyserver]. 

* `KeyServer.LogRoot` - This is a log directory that contains iOS Key Server application logs. If not set, the default is the same as `KeyServer.ConfigRoot` 

* `XboxKeyServer.LogRoot` - This is a log directory that contains the Xbox Key Server application logs. If not set, the default is same as `KeyServer.ConfigRoot`.

If you are using [!DNL catalina.bat] or [!DNL catalina.sh] to start Tomcat, these system properties can easily be set using the `JAVA_OPTS` environment variable. Any Java options set here will be used when Tomcat is started. For example, set: 

```
JAVA_OPTS=-DKeyServer.ConfigRoot=”absolute-path-to-config-folder” 
  -DKeyServer.LogRoot=”absolute-path-to-log-folder”
```

