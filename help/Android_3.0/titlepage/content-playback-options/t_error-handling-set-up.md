---
description: You can set up one lace to handle errors.
seo-description: You can set up one lace to handle errors.
seo-title: Set up error handling
title: Set up error handling
uuid: 2268cb6f-8c46-48dc-a0e3-6f871882ae3a
index: y
internal: n
snippet: y
translate: y
---

# Set up error handling

You can set up one lace to handle errors.


1. Implement an event callback function for `MediaPlayerEvent.STATUS_CHANGED`.

   TVSDK passes event information, such as a `MediaPlayerStatusChangeEvent` object.
1. In the callback, when the returned status is `MediaPlayerStatus.ERROR`, provide logic to handle all errors.
1. After the error is handled, reset the `MediaPlayer` object or load a new media resource.

   When the `MediaPlayer` object is in the error status it remains in that status until you reset it using the `MediaPlayer.reset` method. 

For example: 
```
javamediaPlayer.addEventListener(MediaPlayerEvent.STATUS_CHANGED,  
  new StatusChangeEventListener() { 
    @Override 
    public void onStatusChanged(MediaPlayerStatusChangeEvent event) { 
        if (event.getStatus() == MediaPlayerStatus.ERROR) { 
        // handle TVSDK error here 
        } 
    } 
});
```

