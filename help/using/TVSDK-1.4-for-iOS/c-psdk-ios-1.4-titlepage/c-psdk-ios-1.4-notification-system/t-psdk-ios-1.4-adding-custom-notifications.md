---
seo-title: Add custom notifications
title: Add custom notifications
uuid: ca8e087c-eeb1-427e-8896-cb81098f8b0e
index: y
internal: n
snippet: y
---

# Add custom notifications{#add-custom-notifications}

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

