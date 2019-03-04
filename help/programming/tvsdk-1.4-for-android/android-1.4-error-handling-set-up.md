---
description: Set up a single place to handle errors.
seo-description: Set up a single place to handle errors.
seo-title: Set up error handling
title: Set up error handling
uuid: a3182fce-85ac-4dad-bdb3-f9bfbdb2c62d
---

# Set up error handling{#set-up-error-handling}

Set up a single place to handle errors.

1. Implement an event callback function for `MediaPlayerEvent.STATUS_CHANGED`.

   TVSDK passes event information, such as a `MediaPlayerStatusChangeEvent` object.
1. In the callback, when the returned state is `MediaPlayerState.ERROR`, provide logic to handle all errors.
1. After the error is handled, reset the `MediaPlayer` object or load a new media resource.

   When the `MediaPlayer` object is in the error state, it remains in that state until you reset it using the `MediaPlayer.reset` method.

<!--<a id="example_49FF225E92EA494AA06B2E5F26101F4C"></a>-->

For example: 

```java
mediaPlayer.addEventListener( 
  MediaPlayerEvent.STATUS_CHANGED, new StatusChangedEventListener() { 
    @Override 
    public void onStatusChanged(MediaPlayerStatusChangeEvent event) { 
        if (event.getStatus() == MediaPlayerStatus.ERROR) { 
            // handle TVSDK error here 
        } 
    } 
});
```

