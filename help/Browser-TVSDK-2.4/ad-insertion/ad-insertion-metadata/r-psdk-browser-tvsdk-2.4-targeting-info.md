---
description: In Adobe Primetime ad decisioning, you can target ads on key-value pairs.
seo-description: In Adobe Primetime ad decisioning, you can target ads on key-value pairs.
seo-title: Targeting information
title: Targeting information
uuid: c1b195d8-13a2-48a6-95d0-9316b42515a3
index: y
internal: n
snippet: y
---

# Targeting information{#targeting-information}

In Adobe Primetime ad decisioning, you can target ads on key-value pairs.

 To pass these key value pairs to Browser TVSDK: 

```js
var auditudeSettings = new AdobePSDK.AuditudeSettings(); 
var targetingInfo = new AdobePSDK.Metadata(); 
 
// Add key value pairs to targetingInfo 
targetingInfo.setValue(key1, value1); 
targetingInfo.setValue(key2, value2); 
 
auditudeSettings.targetingInfo = targetingInfo;
```

