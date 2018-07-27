---
description: If you experience compilation errors due to missing Flash library classes, such as flash.events.Event, it is possible that IntelliJ IDEA is building with the wrong playerglobal.swc, even though the project configuration is correct.
seo-description: If you experience compilation errors due to missing Flash library classes, such as flash.events.Event, it is possible that IntelliJ IDEA is building with the wrong playerglobal.swc, even though the project configuration is correct.
seo-title: Troubleshooting compilation errors
title: Troubleshooting compilation errors
uuid: 861c503d-5ee6-4fdb-85e1-cf09ef36e308
index: n
internal: n
snippet: y
translate: y
---

# Troubleshooting compilation errors

To fix this problem:

>1. From the top menu, select ** `File` ** &gt; ** `Project Structure` **.
>1. Under ** `Platform Settings` **, select ** `SDKs` **.
>1. Select the Flex SDK.
>1. Select the ** `Classpath` ** tab and remove the 11.1 version of `playerglobal.swc`.
>   There should only be one version of `playerglobal.swc`, version 11.9 or later.>
>1. Click ** `OK` ** to accept the changes.
>1. From the top menu, select ** `Build` ** &gt; ** `Rebuild Project` **.
