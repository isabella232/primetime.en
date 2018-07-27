---
description: You can set up one lace to handle errors.
seo-description: You can set up one lace to handle errors.
seo-title: Set up error handling
title: Set up error handling
uuid: 5aca6294-5307-48fd-ad6b-47b40aa9650f
index: n
internal: n
snippet: y
translate: y
---

# Set up error handling


>1. Implement an event callback function for ` MediaPlayerEvent.STATUS_CHANGED`.
>   <!-- PH element: phrases/primetime-sdk-name --> passes event information, such as a ` MediaPlayerStatusChangeEvent` object.>
>1. In the callback, when the returned status is ` MediaPlayerStatus.ERROR`, provide logic to handle all errors.
>1. After the error is handled, reset the ` MediaPlayer` object or load a new media resource.
>   When the ` MediaPlayer` object is in the error status it remains in that status until you reset it using the ` MediaPlayer.reset` method. 
>
