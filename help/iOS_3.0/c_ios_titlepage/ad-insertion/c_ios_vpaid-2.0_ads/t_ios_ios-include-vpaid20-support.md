---
description: null
seo-description: null
seo-title: Implement VPAID 2.0 integration
title: Implement VPAID 2.0 integration
uuid: 4690c691-4157-4386-b75f-80c77917c87a
index: y
internal: n
snippet: y
translate: y
---

# Implement VPAID 2.0 integration

To add VPAID 2.0 support in your iOS application: 

1. (Optional) Add a listener for custom ad events.

   ```
   [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(onMediaPlayerCustomAdNotification:) name:PTMediaPlayerCustomAdNotification object:self.player];
   ```

1. (Optional) Display the notification.

   ```
   -(void)onMediaPlayerCustomAdNotification:(NSNotification *)notification{    PTCustomAdNotificationObject *notificationObject = [notification.userInfo objectForKey:PTCustomAdNotificationObjectKey];    if (notificationObject)    
   {        NSLog(@"ViewController:: Custom Ad Notification Received: %ld", notificationObject.type);    } 
    
   }
   ```

