---
description: The Desktop HLS version of the Primetime reference implementation requires Adobe Flex SDK 4.6.0.
seo-description: The Desktop HLS version of the Primetime reference implementation requires Adobe Flex SDK 4.6.0.
seo-title: Install and set up the Flex SDK
title: Install and set up the Flex SDK
---

# Install and set up the Flex SDK

>1. Download the Flex SDK from [http://www.adobe.com/devnet/flex/flex-sdk-download.html](http://www.adobe.com/devnet/flex/flex-sdk-download.html).
>   
>1. Unpack the archive file to a location of your choice.
>   When you unpack the archive, it will create a parent directory of`codeph flex_sdk_4.6`.
>   
>1. Download the `codeph playerglobal.swc`, version 11.9 or later, from [http://www.adobe.com/support/flashplayer/downloads.html](http://www.adobe.com/support/flashplayer/downloads.html).
>   The Primetime SDK libraries use classes and objects in the latest Flash Player release, so it is necessary to add the latest version of the Flash Player's`filepath playerglobal.swc` to the Flex SDK. After you download the swc, do the following:
>   >1. If you haven't already done so, download and install the corresponding Flash Player debugger from [http://www.adobe.com/support/flashplayer/downloads.html](http://www.adobe.com/support/flashplayer/downloads.html).
>   >   
>   >1. Create a folder in your Flex SDK's `filepath frameworks/lib/player` path with the version number of the `filepath playerglobal.swc` as the name.
>   >   For example,`filepath 11.9`.
>   >   
>   >1. Move the `filepath playerglobal.swc` into this folder and rename the file to `filepath playerglobal.swc`.
>   >   
>   >   
>   >[!NOTE]
>   >
>   >If you are using a Flash Player version that is newer than 11.9, you might need to change the target player version under the Dependencies tab of the build configuration for each project.
>   
>   
>   
