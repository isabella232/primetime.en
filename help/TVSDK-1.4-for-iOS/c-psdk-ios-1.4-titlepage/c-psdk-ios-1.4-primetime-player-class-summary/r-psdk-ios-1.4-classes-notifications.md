---
description: These classes describe messages about errors, warnings, and some activities that the TVSDK issues for logging and debugging purposes.
seo-description: These classes describe messages about errors, warnings, and some activities that the TVSDK issues for logging and debugging purposes.
seo-title: Notification classes
title: Notification classes
uuid: 82b4facd-8ee5-44d5-a5c7-9a76d0122742
index: y
internal: n
snippet: y
---

# Notification classes{#notification-classes}

These classes describe messages about errors, warnings, and some activities that the TVSDK issues for logging and debugging purposes.

|  Class name  | Description  |
|---|---|
| [PTMediaError](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTMediaError.html)  |Class that describes the notification for an error that causes the player to stop playback. This is a [PTNotification](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTNotification.html) of notification type ERROR.  |
| [PTMediaPlayerNotifications](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTMediaPlayerNotifications.html)  | Lists all the notifications dispatched by the Primetime Player framework.  |
| [PTNotification](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTNotification.html)  |Class that provides informational messages, warnings, and errors. Encapsulates the object representation of a single notification event within [PTNotificationHistory](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTNotificationHistory.html).  |
| [PTNotificationHistory](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTNotificationHistory.html)  |Class that stores a log of notification objects [PTNotificationHistoryItem](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTNotificationHistoryItem.html) objects that provides access to a notification events history list. That is, it maintains a list of elements, each element containing a separate instance of the [PTNotification](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTNotification.html)  |
| [PTNotificationHistoryItem](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTNotificationHistoryItem.html)  |Class that defines an entry in the circular list in [PTNotificationHistory](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTNotificationHistory.html) and holds the notification and its timestamp.  |

