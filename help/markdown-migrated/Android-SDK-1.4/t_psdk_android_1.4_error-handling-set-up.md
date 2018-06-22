---
description: Set up a single place to handle errors.
seo-description: Set up a single place to handle errors.
seo-title: Set up error handling
title: Set up error handling
---

# Set up error handling

>1. Implement an event callback function for `codeph  MediaPlayerEvent.STATUS_CHANGED`.
>   passes event information, such as a`codeph  MediaPlayerStatusChangeEvent` object.
>   
>1. In the callback, when the returned state is `codeph  MediaPlayerState.ERROR`, provide logic to handle all errors.
>   
>1. After the error is handled, reset the `codeph  MediaPlayer` object or load a new media resource.
>   When the `codeph  MediaPlayer` object is in the error state it remains in that state until you reset it using the `codeph  MediaPlayer.reset` method.
>   
>   
>   
>   
