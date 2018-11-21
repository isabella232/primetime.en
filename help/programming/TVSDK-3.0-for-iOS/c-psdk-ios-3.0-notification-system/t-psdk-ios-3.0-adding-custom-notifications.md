---
seo-title: Add custom notifications
title: Add custom notifications
uuid: ecb5857f-3b3d-4306-b448-e9bd05fad269
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

