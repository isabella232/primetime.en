---
seo-title: Adding custom notifications
title: Adding custom notifications
---

# Adding custom notifications

To add a custom notification:
>1. Create a new `codeph  PTNotification` and add it to the `codeph  PTNotificationHistory` by using the current `codeph  PTMediaPlayerItem`:
>   ```
>   //Access to the PTMediaPlayerItem 
>   PTMediaPlayerItem *item = self.player.currentItem; 
>   PTNotificationHistory *notificationHistory = item.notificationHistory; 
>    
>   //Create notification 
>   PTNotification* notification = [[PTNotification notificationWithType:PTNotificationTypeWarning code:99999 description:@"Custom notification description"]; 
>    
>   //Add notification 
>   [notificationHistory addNotification:notification];
>   ```
>   
>   
>   
