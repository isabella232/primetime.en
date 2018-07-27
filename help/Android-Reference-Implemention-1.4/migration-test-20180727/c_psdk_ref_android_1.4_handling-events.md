---
description: If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.
seo-description: If the application needs to handle events dispatched from the feature manager, it needs to register the manager in the PlayerFragment.java file.
seo-title: Handling events
title: Handling events
uuid: d7cc2a27-a53d-4ba6-a27c-53bfecb8f970
index: n
internal: n
snippet: y
translate: y
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
