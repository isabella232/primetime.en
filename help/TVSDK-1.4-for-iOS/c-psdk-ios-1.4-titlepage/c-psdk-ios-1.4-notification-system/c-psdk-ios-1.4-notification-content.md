---
description: PTNotification provides information that is related to the player’s status.
seo-description: PTNotification provides information that is related to the player’s status.
seo-title: Notification content
title: Notification content
uuid: 11732d84-1164-47ec-aad2-24de033f2a2a
index: y
internal: n
snippet: y
---

# Notification content{#notification-content}

PTNotification provides information that is related to the player’s status.

TVSDK provides a chronological list of `PTNotification` notifications. Each notification contains the following information:

* Time stamp 
* Diagnostic metadata that consists of the following elements:

    * `type`: INFO, WARN, or ERROR. 
    * `code`: A numerical representation of the notification. 
    * `name`: A human-readable description of the notification, such as SEEK_ERROR 
    * `metadata`: Key/value pairs that contain relevant information about the notification. For example, a key named `URL` provides a value that is a URL related to the notification. 
    
    * `innerNotification`: A reference to another `PTNotification` object that directly impacts this notification.

You can store this information locally for later analysis or send it to a remote server for logging and graphical representation. 
