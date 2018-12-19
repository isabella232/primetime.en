---
seo-title: Deploying the Primetime DRM Key Server overview
title: Deploying the Primetime DRM Key Server overview
uuid: 842fdf40-fe2b-4cfd-b27c-fef5dfcc887a
index: y
internal: n
snippet: y
---

# Deploying the Primetime DRM Key Server overview{#deploying-the-primetime-drm-key-server-overview}

Before deploying the Primetime DRM Key Server, make sure that you have installed the required versions of Java and Tomcat. See, [](c_drm_key_server-requirements.md).

The Primetime DRM Key Server download includes [!DNL faxsks.war]. To deploy this WAR file, copy the file to Tomcat’s [!DNL webapps] directory. If you have previously deployed the WAR file, you may need to manually delete the unpacked WAR directory, [!DNL faxsks] in Tomcat’s [!DNL webapps] directory). To prevent Tomcat from unpacking WAR files, edit the [!DNL server.xml] file in Tomcat’s [!DNL conf] directory and set the `unpackWARs` attribute to `false`.

The Primetime DRM Key Server optionally uses a platform-specific library ( [!DNL jsafe.dll] on Windows or [!DNL libjsafe.so] on Linux) for improved performance. Copy the appropriate library for your platform from [!DNL thirdparty/cryptoj/platform] to a location specified by the `PATH` environment variable (or `LD_LIBRARY_PATH` on Linux).

>[!NOTE] {class="- topic/note "}
>
>The 64-bit version of the [!DNL jsafe] library should only be used if both the operating system and JDK support 64-bit, otherwise use the 32-bit version.
