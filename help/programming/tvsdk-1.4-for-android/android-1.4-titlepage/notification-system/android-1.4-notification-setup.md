---
description: You can listen for notifications and you can add your own notifications to the notification history.
seo-description: You can listen for notifications and you can add your own notifications to the notification history.
seo-title: Set up your notification system
title: Set up your notification system
uuid: caa6a306-dea9-45ee-b0b3-569b5f2527a1
index: y
internal: n
snippet: y
---

# Set up your notification system{#set-up-your-notification-system}

You can listen for notifications and you can add your own notifications to the notification history.

 The core of the Primetime Player notification system is the `Notification` class, which represents a standalone notification.

The `NotificationHistory` class provides a mechanism for accumulating notifications. It stores a log of notification (NotificationHistoryItem) objects that represents a collection of Notifications.

To receive notifications:

* Listen for notifications 
* Add notifications to the notification history

1. Listen for state changes.
1. Implement the `MediaPlayer.PlaybackEventListener.onStateChanged` callback.
1. TVSDK passes two parameters to the callback:

    * The new state ( `MediaPlayer.PlayerState`) 
    * A `MediaPlayerNotification` object

