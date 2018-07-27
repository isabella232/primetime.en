---
description: These classes describe messages about errors, warnings, and some activities that the issues for logging and debugging purposes.
seo-description: These classes describe messages about errors, warnings, and some activities that the issues for logging and debugging purposes.
seo-title: Notification classes
title: Notification classes
uuid: 22a30019-6884-4d88-933d-a9db4c5d884c
index: n
internal: n
snippet: y
translate: y
---

# Notification classes


[com.adobe.mediacore](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/package-summary.html)
[com.adobe.mediacore.session](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/session/package-summary.html)
| Class name |Description |
|---|---|
| `MediaPlayerNotification.[Error](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.Error.html)` |Class that describes the notification for an error that causes the player to stop playback. This is a [MediaPlayerNotification](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.html) of notification type ERROR.  |
| `MediaPlayerNotification.[Info](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.Info.html)`  |Class that describes an informational notification. This is a [MediaPlayerNotification](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.html) of notification type INFO. |
| `MediaPlayerNotification.[Warning](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.Warning.html)`  |Class that describes a warning notification. This is a [MediaPlayerNotification](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.html) of notification type WARNING.  |
| [MediaPlayerNotification](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.html)  |Class that provides informational messages, warnings, and errors. Encapsulates the object representation of a single notification event within [NotificationHistory](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/session/NotificationHistory.html).  |
| `MediaPlayerNotification.[NotificationCode](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.NotificationCode.html)`  |Returns the description associated with the provided notification code. |
| [NotificationHistory](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/session/NotificationHistory.html)  |Class that stores a log of notification objects. A circular list of [NotificationHistory.Item](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/session/NotificationHistory.Item.html) objects that provides access to a notification events history list. That is, it maintains a list of elements, each element containing a separate instance of the [MediaPlayerNotification](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.html) class.   |
| `NotificationHistory.[Item](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/session/NotificationHistory.Item.html)`  |Class that defines an entry in the circular list in [NotificationHistory](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/session/NotificationHistory.html) and holds the notification and its timestamp.  |
| `MediaPlayerNotification.[EntryType](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.EntryType.html)`  |Class that contains the supported notifications types. |

