---
description: You can listen for notifications and you can add your own notifications to the notification history.
seo-description: You can listen for notifications and you can add your own notifications to the notification history.
seo-title: Set up your notification system
title: Set up your notification system
---

# Set up your notification system

The core of the Primetime Player notification system is the Notification class, which represents a standalone notification.
The NotificationHistory class provides a mechanism for accumulating notifications. It stores a log of notification (`codeph NotificationHistoryItem`) objects that represents a collection of Notifications.

To receive notifications:

* Listen for notifications
* Add notifications to the notification history
>1. Listen for state changes.
>   
>1. Implement the `codeph MediaPlayer.StatusChangeEvent.STATUS_CHANGED` event listener.
>   
>1. passes a `codeph MediaPlayer.StatusChangeEvent` instance to the event listener, which contains two parameters:
>* The new state (`codeph MediaPlayer.Status`)
>* A `codeph MediaPlayerNotification` object
>   
>   
>   
