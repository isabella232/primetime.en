---
description: You can implement notification callbacks.
seo-description: You can implement notification callbacks.
seo-title: Implementing notification callbacks
title: Implementing notification callbacks
uuid: 9d7b7d3d-87f5-4c07-b55a-085b5cf7b76f
index: n
internal: n
snippet: y
translate: y
---

# Implementing notification callbacks


>1. Implement the notification callback by getting the ` PTNotification` from the ` NSNotification` user information and reading its values by using ` PTMediaPlayerNotificationKey`:
>
>   ```
>   - (void) onMediaPlayerNotification:(NSNotification *) nsnotification { 
>       PTNotification *notification = [nsnotification.userInfo objectForKey:PTMediaPlayerNotificationKey]; 
>       NSLog(@"Notification: %@", notification); 
>   }
>   ```
>
