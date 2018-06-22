---
seo-title: Listening to notifications
title: Listening to notifications
---

# Listening to notifications

There are two ways to listen to the `codeph  PTNotification` notification in the `codeph  PTMediaPlayer`:

>1. Manually check the `codeph  PTNotificationHistory` of the `codeph  PTMediaPlayerItem` with a timer and check the differences:
>   ```
>   //Access to the PTMediaPlayerItem 
>   PTMediaPlayerItem *item = self.player.currentItem; 
>   PTNotificationHistory *notificationHistory = item.notificationHistory; 
>    
>   //Get the list of notification events from the notification History 
>   NSArray *notifications = notificationHistory.notificationItems;
>   ```
>   
>   
>1. Use the posted [ NSNotification ](https://developer.apple.com/library/mac/%23documentation/Cocoa/Reference/Foundation/Classes/NSNotification_Class/Reference/Reference.html) of the `codeph  PTMediaPlayerPTMediaPlayerNewNotificationEntryAddedNotification`.
>   
>1. Register to the `codeph  NSNotification` by using the instance of the `codeph  PTMediaPlayer` from which you want to get notifications:
>   ```
>   //Register to the NSNotification 
>    
>   [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(onMediaPlayerNotification:) 
>    name:PTMediaPlayerNewNotificationEntryAddedNotification object:self.player];
>   ```
>   
>   
>   
