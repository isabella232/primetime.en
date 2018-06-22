---
description: If you experience compilation errors due to missing Flash library classes, such as flash.events.Event, it is possible that IntelliJ IDEA is building with the wrong playerglobal.swc, even though the project configuration is correct.
seo-description: If you experience compilation errors due to missing Flash library classes, such as flash.events.Event, it is possible that IntelliJ IDEA is building with the wrong playerglobal.swc, even though the project configuration is correct.
seo-title: Troubleshooting compilation errors
title: Troubleshooting compilation errors
---

# Troubleshooting compilation errors

To fix this problem:

>1. From the top menu, select `uicontrol File` &gt; `uicontrol Project Structure`.
>   
>1. Under `uicontrol Platform Settings`, select `uicontrol SDKs`.
>   
>1. Select the Flex SDK.
>   
>1. Select the `uicontrol Classpath` tab and remove the 11.1 version of `codeph playerglobal.swc`.
>   There should only be one version of`codeph playerglobal.swc`, version 11.9 or later.
>   
>1. Click `uicontrol OK` to accept the changes.
>   
>1. From the top menu, select `uicontrol Build` &gt; `uicontrol Rebuild Project`.
>   
>   
