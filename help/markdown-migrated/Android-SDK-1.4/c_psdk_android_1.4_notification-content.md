---
description: MediaPlayerNotification provides information that is related to the player’s status.
seo-description: MediaPlayerNotification provides information that is related to the player’s status.
seo-title: Notification content
title: Notification content
---

# Notification content

provides a chronological list of `codeph MediaPlayerNotification` notifications. Each notification contains the following information:
* Time stamp
* Diagnostic metadata that consists of the following elements:
    * `codeph type`: INFO, WARN, or ERROR.
    * `codeph code`: A numerical representation of the notification.
    * `codeph name`: A human-readable description of the notification, such as SEEK_ERROR
    * `codeph metadata`: Key/value pairs that contain relevant information about the notification. For example, a key named `codeph URL` provides a value that is a URL related to the notification.
    * `codeph innerNotification`: A reference to another `codeph MediaPlayerNotification` object that directly impacts this notification.
  

You can store this information locally for later analysis or send it to a remote server for logging and graphical representation.

