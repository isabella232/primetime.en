---
description: In Adobe Primetime ad decisioning, you can target ads on key-value pairs.
seo-description: In Adobe Primetime ad decisioning, you can target ads on key-value pairs.
seo-title: Targeting information
title: Targeting information
uuid: 72114bef-36a1-4f2d-92e8-59f4885d70d2
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

