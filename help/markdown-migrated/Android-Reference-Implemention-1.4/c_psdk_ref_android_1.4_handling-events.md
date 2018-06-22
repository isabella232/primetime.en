---
description: If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.
seo-description: If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.
seo-title: Handling events
title: Handling events
---

# Handling events

For example:

```
private final AdsManager.AdsManagerEventListener adsManagerEventListener = 
 new AdsManager.AdsManagerEventListener() { 
 
 // add the ads functionality... 
 
} 
 
//Register the listener 
adsManager.addEventListener(adsManagerEventListener);
```
