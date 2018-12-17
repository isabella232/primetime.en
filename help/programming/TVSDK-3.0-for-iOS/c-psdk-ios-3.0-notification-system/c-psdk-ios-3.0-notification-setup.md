---
description: TVSDK sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-description: TVSDK sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-title: Notification setup
title: Notification setup
uuid: 5ddfbeb9-660b-430f-8848-7a822986139f
index: y
internal: n
snippet: y
---

# Notification setup{#notification-setup}

TVSDK sets up the player for basic notifications, although you must complete the same set up for your custom notifications.

There are two implementations for `PTNotification`:

* To listen 
* To add custom notifications to `PTNotificationHistory`

To listen to notifications, TVSDK instantiates the `PTNotification` class and attaches it to an instance of the `PTMediaPlayerItem`, which is attached to a PTMediaPlayer instance. There is only one `PTNotificationHistory` instance per `PTMediaPlayer`.

>[!IMPORTANT]
>
>If you are adding customizations, your applications and not TVSDK, must perform those steps.

