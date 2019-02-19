---
seo-title: Add custom notifications
title: Add custom notifications
uuid: 4b48db70-7188-4c79-9428-8cbf45ef15f0
---

# Add custom notifications{#add-custom-notifications}

 To add a custom notification: 
   Create a new `PTNotification` and add it to the `PTNotificationHistory` by using the current `PTMediaPlayerItem`:

   ```
   //Access to the PTMediaPlayerItem  
   PTMediaPlayerItem *item = self.player.currentItem; 
   PTNotificationHistory *notificationHistory = item.notificationHistory; 
    
   //Create notification 
   PTNotification* notification = [[PTNotification notificationWithType:PTNotificationTypeWarning code:99999 description:@"Custom notification description"]; 
    
   //Add notification 
   [notificationHistory addNotification:notification];
   ```