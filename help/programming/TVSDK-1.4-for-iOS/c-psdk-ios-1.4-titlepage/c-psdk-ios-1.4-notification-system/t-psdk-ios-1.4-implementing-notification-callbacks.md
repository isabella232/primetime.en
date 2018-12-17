---
description: You can implement notification callbacks.
seo-description: You can implement notification callbacks.
seo-title: Implement notification callbacks
title: Implement notification callbacks
uuid: 2cfa11db-cd75-4f53-ab41-a305838a9b76
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

