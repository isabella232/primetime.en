---
description: MediaPlayerNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-description: MediaPlayerNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.
seo-title: Notifications for player status, activity, errors, and logging
title: Notifications for player status, activity, errors, and logging
uuid: 7ce5bed0-f312-437e-a82f-b1d4a8e1926c
---

# Notifications for player status, activity, errors, and logging{#notifications-for-player-status-activity-errors-and-logging}

MediaPlayerNotification objects provide information about changes in player status, warnings, and errors. Errors that stop the playback of the video also cause a change in the status of the player.

Your application can retrieve the notification and status information. You can also create a logging system for diagnostics and validation by using the notification information.

You implement event listeners to capture and respond to events. Many events provide `MediaPlayerNotification` status notifications. 
