---
description: If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.
seo-description: If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.
seo-title: Handling events
title: Handling events
uuid: 13639f02-0dcc-4a0a-8524-515da5478006
---

# Handling events {#handling-events}

If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.

For example:

```
private final AdsManager.AdsManagerEventListener adsManagerEventListener =  
  new AdsManager.AdsManagerEventListener() { 
 
    // add the ads functionality... 
 
} 
 
//Register the listener 
adsManager.addEventListener(adsManagerEventListener);
```