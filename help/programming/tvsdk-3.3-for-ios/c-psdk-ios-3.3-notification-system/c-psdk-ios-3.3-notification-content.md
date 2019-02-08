---
description: PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-description: PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-title: Notification content
title: Notification content
uuid: d42d2e89-1bdd-4be0-8a69-821fec6bbc75
---

# Notification content {#notification-content}

`PTNotification` objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.

Your application can retrieve the notification and status information. You can also create a logging system for diagnostics and validation by using the notification information.

>[!NOTE]
>
>TVSDK also uses *`notification`* to refer to `NSNotifications` ( `PTMediaPlayer` notifications) *`event`* notifications, dispatched to provide information about player activity.

TVSDK also issues `PTMediaPlayerNewNotificationItemEntryNotification` when it issues `PTNotification`.

You implement event listeners to capture and respond to events. Many events provide `PTNotification` status notifications.

<!--<a id="section_8D751C71BE80402EB7F6152BA220A006"></a>-->

`PTNotification` provides information that is related to the player’s status.

TVSDK provides a chronological list of `PTNotification` notifications. Each notification contains the following information:

* Time stamp 
* Diagnostic metadata that consists of the following elements:

    * `type`: INFO, WARN, or ERROR. 
    * `code`: A numerical representation of the notification. 
    * `name`: A human-readable description of the notification, such as SEEK_ERROR 
    * `metadata`: Key/value pairs that contain relevant information about the notification. For example, a key named `URL` provides a value that is a URL related to the notification. 
    
    * `innerNotification`: A reference to another `PTNotification` object that directly impacts this notification.

You can store this information locally for later analysis or send it to a remote server for logging and graphical representation.