---
description: Set up a single place to handle errors.
seo-description: Set up a single place to handle errors.
seo-title: Set up error handling
title: Set up error handling
uuid: 37224227-cbd6-4512-95f3-3d9eee2755ff
index: n
internal: n
snippet: y
translate: y
---

# Set up error handling


>1. Implement an event callback function for ` MediaPlayerStatusChangeEvent.STATUS_CHANGED`.
>   <!-- PH element: phrases/primetime-sdk-name --> passes event information, such as a ` MediaPlayerStatusChangeEvent` object.>
>1. In the callback, when the status from the event parameter is ` MediaPlayerStatus.ERROR`, provide logic to handle all errors.
>1. After the error is handled, reset the ` MediaPlayer` object or load a new media resource.
>   When the ` MediaPlayer` object is in the ERROR state, it cannot exit this state until you either reset the ` MediaPlayer` object (via the ` MediaPlayer.reset` method) or load a new media resource ( ` MediaPlayer.replaceCurrentItem`). 
>
