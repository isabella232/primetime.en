---
description: TVSDK sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-description: TVSDK sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-title: Notification setup
title: Notification setup
uuid: ea0544f2-b507-4937-b35e-16d1d5e2b4bd
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

