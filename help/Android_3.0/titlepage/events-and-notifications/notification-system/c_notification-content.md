---
description: MediaPlayerNotification provides information that is related to the player’s status.
seo-description: MediaPlayerNotification provides information that is related to the player’s status.
seo-title: Notification content
title: Notification content
uuid: b1acb328-2c2b-4a04-9685-3d5cb51a19e8
index: y
internal: n
snippet: y
translate: y
---

# Notification content

MediaPlayerNotification provides information that is related to the player’s status.

TVSDK provides a chronological list of `MediaPlayerNotification` notifications, and each notification contains the following information: 
* A time stamp
* Diagnostic metadata that consists of the following elements: 
    * `type`: INFO, WARN, or ERROR.    
    * `code`: A numerical representation of the notification.    
    * `name`: A human-readable description of the notification, such as SEEK_ERROR    
    * `metadata`: Key/value pairs that contain relevant information about the notification. For example, a key named `URL` provides a value that is a URL related to the notification.    
    * `innerNotification`: A reference to another `MediaPlayerNotification` object that directly impacts this notification.    
    
    





You can store this information locally for later analysis or send it to a remote server for logging and graphical representation. 
