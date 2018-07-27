---
description: You can listen for notifications.
seo-description: You can listen for notifications.
seo-title: Set up your notification system
title: Set up your notification system
uuid: 4fe37ecb-75d6-455a-adb6-e57253ac2b7d
index: n
internal: n
snippet: y
translate: y
---

# Set up your notification system

The core of the Primetime Player notification system is the `Notification` class, which represents a standalone notification. <!-- No such thing as NotificationHistory in 2.X, I don't think. This whole topic is dubious at best.
<p>The <span class="codeph">NotificationHistory</span> class provides a mechanism for accumulating notifications. It stores a log of notification (<span class="codeph">NotificationHistoryItem</span>) objects that represents a collection of notifications. </p> --> To receive notifications, listen for notifications as follows:

>1. Implement the `NotificationEventListener.onNotification()` callback.
>1. <!-- PH element: phrases/primetime-sdk-name --> passes a `NotificationEvent` object to the callback.
>       Notifications types are enumerated in the `Notification.Type` enum:>    
>    * `ERROR`
>    * `INFO`
>    * `WARNING`
>    
