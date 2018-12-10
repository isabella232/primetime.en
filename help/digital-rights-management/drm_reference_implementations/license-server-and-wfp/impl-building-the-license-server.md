---
description: null
seo-description: null
seo-title: Build the license server
title: Build the license server
uuid: 64379fcc-861f-4133-88ee-d3364aea1e0c
index: y
internal: n
snippet: y
---

# Build the license server{#build-the-license-server}

>[!NOTE] {class="- topic/note "}
>
>Building the license server is only necessary if you intend to modify the source code. For evaluation purposes, you can simply use the WAR files as shipped.

The reference implementation license server includes all of the license server source code ( `([DRM SDK DVD]\Reference Implementation\Server\Reference Implementation Server\src/`), along with an Ant build script ( `[DRM SDK DVD]\Reference Implementation\Server\Reference Implementation Server\refimpl/build-refimpl.xml`) with which you can customize the license server to suit your business needs. 

1. Modify the Ant build script to specify the locations of your Primetime DRM SDK, Tomcat, MySQL, and Log4J.

       Open the [!DNL build-refimpl.xml] file in a text editor and set these property values:

    * `sdkdir` 
    * `tomcatdir` 
    * `mysqldir` 
    * `log4jdir`

1. Run the Ant build script with the `all` property, in the directory where the Ant build script is located.

   ```
   ant -f build-refimpl.xml all
   ```

   The Ant build script creates a [!DNL refimpl-build/wars] directory that includes the server WAR files.
