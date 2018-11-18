---
description: In Adobe Primetime ad decisioning, you can target ads on key-value pairs.
seo-description: In Adobe Primetime ad decisioning, you can target ads on key-value pairs.
seo-title: Targeting information
title: Targeting information
uuid: ab35e7d4-5322-4a10-b853-e3474a40e3dd
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

