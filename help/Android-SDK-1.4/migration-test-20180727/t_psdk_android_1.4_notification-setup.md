---
description: You can listen for notifications and you can add your own notifications to the notification history.
seo-description: You can listen for notifications and you can add your own notifications to the notification history.
seo-title: Set up your notification system
title: Set up your notification system
uuid: 733ab18f-1f8d-4688-9ea5-da9ef222cfbc
index: n
internal: n
snippet: y
translate: y
---

# Set up your notification system

The core of the Primetime Player notification system is the `Notification` class, which represents a standalone notification. The `NotificationHistory` class provides a mechanism for accumulating notifications. It stores a log of notification (NotificationHistoryItem) objects that represents a collection of Notifications. 
To receive notifications:

* Listen for notifications
* Add notifications to the notification history

>1. Listen for state changes.
>1. Implement the `MediaPlayer.PlaybackEventListener.onStateChanged` callback.
>1. <!-- PH element: phrases/primetime-sdk-name --> passes two parameters to the callback:
>    
>    * The new state ( `MediaPlayer.PlayerState`)
>    * A `MediaPlayerNotification` object
>    
