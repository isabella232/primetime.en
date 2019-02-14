---
description: You can implement notification callbacks.
seo-description: You can implement notification callbacks.
seo-title: Implement notification callbacks
title: Implement notification callbacks
uuid: 6c7d1fd3-bc4f-40da-a824-7a8eadc8bdda
---

# Implement notification callbacks {#implement-notification-callbacks}

You can implement notification callbacks.

   Implement the notification callback by getting the `PTNotification` from the `NSNotification` user information and reading its values by using `PTMediaPlayerNotificationKey`:

   ```
   - (void) onMediaPlayerNotification:(NSNotification *) nsnotification { 
       PTNotification *notification = [nsnotification.userInfo objectForKey:PTMediaPlayerNotificationKey]; 
       NSLog(@"Notification: %@", notification); 
   }
   ```