---
description: MediaPlayerNotification objects provide information about changes in player state, warnings, and errors. Errors that stop the playback of the video also cause a change in the state of the player.
seo-description: MediaPlayerNotification objects provide information about changes in player state, warnings, and errors. Errors that stop the playback of the video also cause a change in the state of the player.
seo-title: Notification content
title: Notification content
uuid: a135b188-2a0f-4374-8f35-8cc285f4b1e4
index: y
internal: n
snippet: y
---

# Notification content{#notification-content}

MediaPlayerNotification objects provide information about changes in player state, warnings, and errors. Errors that stop the playback of the video also cause a change in the state of the player.

Your application can retrieve the notification and state information. You can also create a logging system for diagnostics and validation by using the notification information.

You implement event listeners to capture and respond to events. Many events provide `MediaPlayerNotification` status notifications.

`MediaPlayerNotification` provides information that is related to the player’s status.

TVSDK provides a chronological list of `MediaPlayerNotification` notifications. Each notification contains the following information:

* Time stamp 
* Diagnostic metadata that consists of the following elements:

    * `type`: INFO, WARN, or ERROR. 
    * `code`: A numerical representation of the notification. 
    * `name`: A human-readable description of the notification, such as SEEK_ERROR 
    * `metadata`: Key/value pairs that contain relevant information about the notification. For example, a key named `URL` provides a value that is a URL related to the notification. 
    
    * `innerNotification`: A reference to another `MediaPlayerNotification` object that directly impacts this notification.

You can store this information locally for later analysis or send it to a remote server for logging and graphical representation. 
