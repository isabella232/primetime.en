---
description: sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-description: sets up the player for basic notifications, although you must complete the same set up for your custom notifications.
seo-title: Notification setup
title: Notification setup
---

# Notification setup

There are two implementations for `codeph PTNotification`:
* To listen
* To add custom notifications to `codeph PTNotificationHistory`
To listen to notifications, instantiates the `codeph PTNotification` class and attaches it to an instance of the `codeph PTMediaPlayerItem`, which is attached to a PTMediaPlayer instance. There is only one `codeph PTNotificationHistory` instance per `codeph PTMediaPlayer`.

>[!IMPORTANT]
>
>If you are adding customizations, your applications and not, must perform those steps.
