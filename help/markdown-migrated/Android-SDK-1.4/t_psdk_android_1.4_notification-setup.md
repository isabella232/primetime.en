---
description: You can listen for notifications and you can add your own notifications to the notification history.
seo-description: You can listen for notifications and you can add your own notifications to the notification history.
seo-title: Set up your notification system
title: Set up your notification system
---

# Set up your notification system

The core of the Primetime Player notification system is the`codeph Notification` class, which represents a standalone notification.
The `codeph NotificationHistory` class provides a mechanism for accumulating notifications. It stores a log of notification (NotificationHistoryItem) objects that represents a collection of Notifications.

To receive notifications:

* Listen for notifications
* Add notifications to the notification history
>1. Listen for state changes.
>   
>1. Implement the `codeph MediaPlayer.PlaybackEventListener.onStateChanged` callback.
>   
>1. passes two parameters to the callback:
>* The new state (`codeph MediaPlayer.PlayerState`)
>* A `codeph MediaPlayerNotification` object
>   
>   
>   
