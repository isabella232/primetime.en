---
description: PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-description: PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-title: Notifications for player status, activity, errors, and logging
title: Notifications for player status, activity, errors, and logging
uuid: 06775691-c5f3-4edc-b0a6-bc7aaaea1f19
index: y
internal: n
snippet: y
translate: y
---

# Notifications for player status, activity, errors, and logging

PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.

Your application can retrieve the notification and status information. You can also create a logging system for diagnostics and validation by using the notification information. 

>[!IMPORTANT]
>
>TVSDK also uses *`notification`* to refer to `NSNotifications` ( `PTMediaPlayer` notifications) *`event`* notifications, dispatched to provide information about player activity. 

TVSDK also issues `PTMediaPlayerNewNotificationItemEntryNotification` when it issues `PTNotification`. 

You implement event listeners to capture and respond to events. Many events provide `PTNotification` status notifications. 
