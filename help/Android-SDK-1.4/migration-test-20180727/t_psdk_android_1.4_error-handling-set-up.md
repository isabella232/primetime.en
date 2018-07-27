---
description: Set up a single place to handle errors.
seo-description: Set up a single place to handle errors.
seo-title: Set up error handling
title: Set up error handling
uuid: 908c9966-5654-4af9-b525-a62f16149817
index: n
internal: n
snippet: y
translate: y
---

# Set up error handling


>1. Implement an event callback function for ` MediaPlayerEvent.STATUS_CHANGED`.
>   <!-- PH element: phrases/primetime-sdk-name --> passes event information, such as a ` MediaPlayerStatusChangeEvent` object.>
>1. In the callback, when the returned state is ` MediaPlayerState.ERROR`, provide logic to handle all errors.
>1. After the error is handled, reset the ` MediaPlayer` object or load a new media resource.
>   When the ` MediaPlayer` object is in the error state it remains in that state until you reset it using the ` MediaPlayer.reset` method. 
>
