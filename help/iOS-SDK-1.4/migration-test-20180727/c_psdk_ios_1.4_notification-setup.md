---
description: sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-description: sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-title: Notification setup
title: Notification setup
uuid: ee79df4c-7d2a-4b8b-905a-93e3d5760e48
index: n
internal: n
snippet: y
translate: y
---

# Notification setup

There are two implementations for `PTNotification`: 
* To listen
* To add custom notifications to `PTNotificationHistory`
To listen to notifications, <!-- PH element: phrases/primetime-sdk-name --> instantiates the `PTNotification` class and attaches it to an instance of the `PTMediaPlayerItem`, which is attached to a PTMediaPlayer instance. There is only one `PTNotificationHistory` instance per `PTMediaPlayer`. 

>[!IMPORTANT]
>
>If you are adding customizations, your applications and not <!-- PH element: phrases/primetime-sdk-name --> , must perform those steps.

