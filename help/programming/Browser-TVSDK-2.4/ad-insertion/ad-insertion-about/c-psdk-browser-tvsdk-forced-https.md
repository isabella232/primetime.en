---
description: null
seo-description: null
seo-title: Secure Ad Loading over HTTPS
title: Secure Ad Loading over HTTPS
uuid: f972b1a5-e54e-47a8-9f07-8f7daffb3d39
index: y
internal: n
snippet: y
---

# Secure Ad Loading over HTTPS{#secure-ad-loading-over-https}

Adobe Primetime can request third-party ad servers over https even if the player is hosted on http. Only those ad-servers calls are upgraded to https that the client seeks during the Auditude Ad resolver phase.

>[!NOTE]
>
>This feature is not supported for Flash.

Use the following to enable secure ad loading. It is not enabled by default. 

```
var auditudeSettings = new AdobePSDK.AuditudeSettings(); 
auditudeSettings.forceHttpsConfiguration.adServerCalls = true;
```

