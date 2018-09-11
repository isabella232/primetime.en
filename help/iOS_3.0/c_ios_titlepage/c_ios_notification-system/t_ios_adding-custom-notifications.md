---
seo-title: Adding custom notifications
title: Adding custom notifications
uuid: 511813c7-b661-4476-b979-8d70db023c28
index: y
internal: n
snippet: y
translate: y
---

# Adding custom notifications

To add a custom notification:
1. Create a new `PTNotification` and add it to the `PTNotificationHistory` by using the current `PTMediaPlayerItem`:

   ```
   //Access to the PTMediaPlayerItem  
   PTMediaPlayerItem *item = self.player.currentItem; 
   PTNotificationHistory *notificationHistory = item.notificationHistory; 
    
   //Create notification 
   PTNotification* notification = [[PTNotification notificationWithType:PTNotificationTypeWarning code:99999 description:@"Custom notification description"]; 
    
   //Add notification 
   [notificationHistory addNotification:notification];
   ```

