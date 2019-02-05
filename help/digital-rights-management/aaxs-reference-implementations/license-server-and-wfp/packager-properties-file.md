---
seo-title: Packager properties file
title: Packager properties file
uuid: 156624ec-66f0-4718-8a66-ed04a47f234d
---

# Packager properties file {#packager-properties-file}

Use the [!DNL flashaccess-refimpl-packager.properties] file to configure the Watched Folder Packager component of the reference implementation. At a minimum, be sure to set the license server URL, license server certificate, packager credential, and key protection options. This file also contains the location of each watched folder (packager.watchfolder.source. `n`). Any changes made to the values in this property file will take effect the next time the watched folder packager runs (restarting the server is not required). However, if there is a configuration error in the packager, the watched folder packager thread will exit, and the server will need to be restarted to restart the packager thread. 
