---
description: You can implement notification callbacks.
seo-description: You can implement notification callbacks.
seo-title: Implementing notification callbacks
title: Implementing notification callbacks
uuid: ba4f51b9-ccd1-4c47-9ce8-4f9ce8e63958
index: y
internal: n
snippet: y
translate: y
---

# Implementing notification callbacks

You can implement notification callbacks.


1. Implement the notification callback by getting the `PTNotification` from the `NSNotification` user information and reading its values by using `PTMediaPlayerNotificationKey`:

   ```
   - (void) onMediaPlayerNotification:(NSNotification *) nsnotification { 
       PTNotification *notification = [nsnotification.userInfo objectForKey:PTMediaPlayerNotificationKey]; 
       NSLog(@"Notification: %@", notification); 
   }
   ```

