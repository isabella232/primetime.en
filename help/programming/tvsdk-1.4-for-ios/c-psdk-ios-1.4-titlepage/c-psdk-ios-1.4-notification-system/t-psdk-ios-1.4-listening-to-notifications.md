---
seo-title: Listen to notifications
title: Listen to notifications
uuid: 1e558e62-a5f4-4962-95b0-5c3695df3cdd
index: y
internal: n
snippet: y
---

# Listen to notifications{#listen-to-notifications}

There are two ways to listen to the `PTNotification` notification in the `PTMediaPlayer`: 

1. Manually check the `PTNotificationHistory` of the `PTMediaPlayerItem` with a timer and check the differences:

   ```
   //Access to the PTMediaPlayerItem  
   PTMediaPlayerItem *item = self.player.currentItem; 
   PTNotificationHistory *notificationHistory = item.notificationHistory; 
    
   //Get the list of notification events from the notification History  
   NSArray *notifications = notificationHistory.notificationItems;
   ```

1. Use the posted [NSNotification](https://developer.apple.com/library/mac/%23documentation/Cocoa/Reference/Foundation/Classes/NSNotification_Class/Reference/Reference.html) of the `PTMediaPlayerPTMediaPlayerNewNotificationEntryAddedNotification`.
1. Register to the `NSNotification` by using the instance of the `PTMediaPlayer` from which you want to get notifications:

   ```
   //Register to the NSNotification 
    
   [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(onMediaPlayerNotification:)  
     name:PTMediaPlayerNewNotificationEntryAddedNotification object:self.player];
   ```

