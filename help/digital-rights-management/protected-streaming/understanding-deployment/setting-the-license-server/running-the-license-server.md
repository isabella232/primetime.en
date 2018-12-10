---
seo-title: Running the DRM Server for Protected Streaming
title: Running the DRM Server for Protected Streaming
uuid: b7218e74-e17c-4b3a-834d-8ec0213001e8
index: y
internal: n
snippet: y
---

# Running the DRM Server for Protected Streaming{#running-the-drm-server-for-protected-streaming}

Before you can start the Adobe Primetime DRM Server for Protected Streaming, it is recommended that you verify the validity of the settings in the configuration files.

You can verify the validity of the settings by using the utilities that have been provided with the license server. (See *Configuration validator* in this guide.

If you want to start Tomcat and the license server, you need to run [!DNL catalina.bat start] or [!DNL catalina.sh start] from Tomcat's [!DNL bin] directory.

After the server has started, you need to verify that it has been correctly configured by opening [!DNL http://<license-server-host:port>/flashaccessserver/<tenant-name>/flashaccess/license/v1] in a browser window. If the tenant configuration has been successfully loaded, a confirmation message appears. 
