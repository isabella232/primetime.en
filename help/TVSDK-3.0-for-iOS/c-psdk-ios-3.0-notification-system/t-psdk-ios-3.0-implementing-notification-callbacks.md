---
description: You can implement notification callbacks.
seo-description: You can implement notification callbacks.
seo-title: Implement notification callbacks
title: Implement notification callbacks
uuid: e9d800fe-dfd8-44f9-83ca-67b96f4ad008
index: y
internal: n
snippet: y
---

# Implement notification callbacks{#implement-notification-callbacks}

You can implement notification callbacks.

1. Implement the notification callback by getting the `PTNotification` from the `NSNotification` user information and reading its values by using `PTMediaPlayerNotificationKey`:

   ```
   - (void) onMediaPlayerNotification:(NSNotification *) nsnotification { 
       PTNotification *notification = [nsnotification.userInfo objectForKey:PTMediaPlayerNotificationKey]; 
       NSLog(@"Notification: %@", notification); 
   }
   ```

