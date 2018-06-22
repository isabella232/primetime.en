---
description: Set up a single place to handle errors.
seo-description: Set up a single place to handle errors.
seo-title: Set up error handling
title: Set up error handling
---

# Set up error handling

>1. Implement an event callback function for `codeph  MediaPlayerStatusChangeEvent.STATUS_CHANGED`.
>   passes event information, such as a`codeph  MediaPlayerStatusChangeEvent` object.
>   
>1. In the callback, when the status from the event parameter is `codeph  MediaPlayerStatus.ERROR`, provide logic to handle all errors.
>   
>1. After the error is handled, reset the `codeph  MediaPlayer` object or load a new media resource.
>   When the `codeph  MediaPlayer` object is in the ERROR state, it cannot exit this state until you either reset the `codeph  MediaPlayer` object (via the `codeph  MediaPlayer.reset` method) or load a new media resource ( `codeph  MediaPlayer.replaceCurrentItem`).
>   
>   
>   
>   
