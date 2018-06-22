---
description: PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-description: PTNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-title: Notifications for player status, activity, errors, and logging
title: Notifications for player status, activity, errors, and logging
---

# Notifications for player status, activity, errors, and logging

Your application can retrieve the notification and status information. You can also create a logging system for diagnostics and validation by using the notification information.

>[!IMPORTANT]
>
>also uses `term notification` to refer to `codeph NSNotifications` (`codeph PTMediaPlayer` notifications) `term event` notifications, dispatched to provide information about player activity.
>
>
also issues `codeph PTMediaPlayerNewNotificationItemEntryNotification` when it issues `codeph PTNotification`.

You implement event listeners to capture and respond to events. Many events provide `codeph PTNotification` status notifications.

