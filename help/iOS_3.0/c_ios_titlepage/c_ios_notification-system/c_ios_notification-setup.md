---
description: TVSDK sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-description: TVSDK sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-title: Notification setup
title: Notification setup
uuid: ae773344-38ac-4d52-a350-e0f97b0faf7e
index: y
internal: n
snippet: y
translate: y
---

# Notification setup

TVSDK sets up the player for basic notifications, although you must complete the same set up for your custom notifications.

There are two implementations for `PTNotification`: 
* To listen* To add custom notifications to `PTNotificationHistory`


To listen to notifications, TVSDK instantiates the `PTNotification` class and attaches it to an instance of the `PTMediaPlayerItem`, which is attached to a PTMediaPlayer instance. There is only one `PTNotificationHistory` instance per `PTMediaPlayer`. 

>[!IMPORTANT]
>
>If you are adding customizations, your applications and not TVSDK, must perform those steps.
