---
seo-title: About ECI Files
title: About ECI Files
uuid: 124d8ab1-933b-4a1b-992a-919f3d799460
---

# About ECI Files{#about-eci-files}

In addition to the CRLs, you also need to periodically update Embedded Common Interface (ECI) files. Whenever Adobe adds support for a new Primetime DRM client platform (for example: iOS, Android, Windows FlashPlayer, etc.), a new ECI record is created. In order to support the individualization of this client, a corresponding ECI record needs to be present on the Individualization Server.

Since the release of new Primetime DRM clients is not very frequent, Adobe will be releasing updated ECI data on an as needed basis. Periodically, Adobe will collect ECI files and host them to the location below for distribution:

The [!DNL Latest.txt] file will contain the URL to the most recent CRL distribution file.

Adobe will create the ECI zip file in the manner described below:

Folder Structure:

The contents of the folder will be zipped up recursively:

An OpenSSL SHA-­-256 digest will be calculated of the zip file:

The zip file will be renamed to contain the archive date as well as the SHA-256 digest:

For example:

You should periodically check the location above for updated ECI files.

Perform the following process for installation after download:

1. Note the SHA-256 digest and recalculate it using OpenSSL or an equivalent tool. 
1. Compare it to the one specified in the file name. 
1. Rename the file to [!DNL ECI.zip]. 
1. Unzip the [!DNL ECI] directory. 
1. Replace the old ECI directory with the new one. 
1. Restart the Individualization server.

