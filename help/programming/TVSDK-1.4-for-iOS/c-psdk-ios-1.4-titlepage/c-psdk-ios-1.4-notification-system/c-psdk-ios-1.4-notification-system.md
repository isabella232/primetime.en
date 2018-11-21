---
description: PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-description: PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-title: Notifications for player status, activity, errors, and logs
title: Notifications for player status, activity, errors, and logs
uuid: 7b900a8e-f307-4a75-9687-358e75fda36b
index: y
internal: n
snippet: y
---

# Notifications for player status, activity, errors, and logs{#notifications-for-player-status-activity-errors-and-logs}

PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.

Your application can retrieve the notification and status information. You can also create a logging system for diagnostics and validation by using the notification information.

>[!IMPORTANT]
>
>TVSDK also uses *`notification`* to refer to `NSNotifications` ( `PTMediaPlayer` notifications) *`event`* notifications, dispatched to provide information about player activity.

TVSDK also issues `PTMediaPlayerNewNotificationItemEntryNotification` when it issues `PTNotification`.

You implement event listeners to capture and respond to events. Many events provide `PTNotification` status notifications. 
