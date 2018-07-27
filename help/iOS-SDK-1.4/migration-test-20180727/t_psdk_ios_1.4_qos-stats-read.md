---
description: You can read playback, buffering, and device statistics from the PTQOSProvider class.
seo-description: You can read playback, buffering, and device statistics from the PTQOSProvider class.
seo-title: Read QOS playback, buffering, and device statistics
title: Read QOS playback, buffering, and device statistics
uuid: 885f9fb1-6f77-421d-b964-dc5d1326a356
index: n
internal: n
snippet: y
translate: y
---

# Read QOS playback, buffering, and device statistics

The ` PTQOSProvider` class provides various statistics, including information about buffering, bit rates, frame rates, time data, and so on. 
It also provides information about the device, such as the model, operating system, and manufacturer's device ID.

>[!TIP]
>
>You cannot change the playback buffer size, but you can monitor the status of the buffer size for debugging or analysis. ` PTPlaybackInformation` includes such properties as ` playbackBufferFull` and ` playbackLikelyToKeepUp`. 


>1. Instantiate a media player.
>1. Create a ` PTQOSProvider` object and attach it to the media player.
>   The ` PTQOSProvider` constructor takes a player context so that it can retrieve device-specific information. 
>
>   ```
>   qosProvider = [[PTQOSProvider alloc]initWithPlayer:self.player];
>   ```
>
>1. (Optional) Read the playback statistics.
>   One solution to read playback statistics is to have a timer, such as an ` NSTimer`, that periodically fetches the new QoS values from the ` PTQOSProvider`. For example: >
>   ```
>   - (void)printPlaybackInfoLog { 
>       PTPlaybackInformation *playbackInfo = qosProvider.playbackInformation;  
>       if (playbackInfo) { 
>           // For example: 
>           NSString *infoLog = [NSString stringWithFormat:@"observedBitrate :  
>                                  %f\n",playbackInfo.observedBitrate]; 
>           [consoleView logMessage:@"====%@\n\n",infoLog]; 
>       } 
>   }
>   ```

>
>1. (Optional) Read the device-specific information.
>
>   ```
>    PTDeviceInformation *devInfo = qosProvider.deviceInformation; 
>   if (devInfo) { 
>       [consoleView logMessage:@"=== qosDeviceInfo:==\n os =%@\n model =  
>          %@\n id =%@\n\n", devInfo.os, devInfo.model, devInfo.id]; 
>   } 
>   [NSTimer scheduledTimerWithTimeInterval:2.0 target:self  
>      selector:@selector(printPlaybackInfoLog) userInfo:nil repeats:YES];
>   ```
>
