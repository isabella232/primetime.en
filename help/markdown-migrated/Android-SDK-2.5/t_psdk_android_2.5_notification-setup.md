---
description: You can listen for notifications.
seo-description: You can listen for notifications.
seo-title: Set up your notification system
title: Set up your notification system
---

# Set up your notification system

The core of the Primetime Player notification system is the`codeph Notification` class, which represents a standalone notification. <!-- No such thing as NotificationHistory in 2.X, I don't think. This whole topic is dubious at best.
<p>The <span class="codeph">NotificationHistory</span> class provides a mechanism for accumulating notifications. It stores a log of notification (<span class="codeph">NotificationHistoryItem</span>) objects that represents a collection of notifications. </p> -->
To receive notifications, listen for notifications as follows:

>1. Implement the `codeph NotificationEventListener.onNotification()` callback.
>   
>1. passes a `codeph NotificationEvent` object to the callback.
>   Notifications types are enumerated in the`codeph Notification.Type` enum:
>* `codeph ERROR`
>* `codeph INFO`
>* `codeph WARNING`
>   
>   
>   
