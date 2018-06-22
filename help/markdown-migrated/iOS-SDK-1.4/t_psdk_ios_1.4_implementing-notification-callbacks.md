---
description: You can implement notification callbacks.
seo-description: You can implement notification callbacks.
seo-title: Implementing notification callbacks
title: Implementing notification callbacks
---

# Implementing notification callbacks

>1. Implement the notification callback by getting the `codeph  PTNotification` from the `codeph  NSNotification` user information and reading its values by using `codeph  PTMediaPlayerNotificationKey`:
>   ```
>   - (void) onMediaPlayerNotification:(NSNotification *) nsnotification { 
>    PTNotification *notification = [nsnotification.userInfo objectForKey:PTMediaPlayerNotificationKey]; 
>    NSLog(@"Notification: %@", notification); 
>   }
>   ```
>   
>   
>   
