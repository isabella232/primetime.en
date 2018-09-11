---
description: null
seo-description: null
seo-title: Configure adaptive bit rates
title: Configure adaptive bit rates
uuid: fd4d3d72-9a30-4883-92c1-7af70d9c0f00
index: y
internal: n
snippet: y
translate: y
---

# Configure adaptive bit rates

To configure TVSDK adaptive bit-rate parameters: 

1. Configure an instance of `PTABRControlParameters` to set the initial, minimum, and maximum bit-rate settings.

   The default values are displayed in the following code snippet, but your application can set any integer value for each of these parameters. 
   >[!IMPORTANT]
   >
   >Specify the bit-rate settings in bits-per-second (bps).

   ```
   // ARC (add autorelease for non-ARC) 
   PTABRControlParameters *abrMetaData =  
       [[PTABRControlParameters alloc] init];  
    
   abrMetaData.initialBitRate = -1; 
   abrMetaData.minBitRate = 0; 
   abrMetaData.maxBitRate = INT_MAX;
   ```


1. Update your `PTMediaPlayer` instance with the configured `PTABRControlParameters` instance.

   ```
   // assuming self.player is the PTMediaPlayer instance 
   self.player.abrControlParameters = abrMetaData;
   ```

Remember the following: 
* The application must set the `abrControlParameters` property on `PTMediaPlayer` before configuring a `PTMediaPlayerItem` instance for the initial and minimum bitrate settings to take effect. After content playback starts, setting a new instance only affects the maximum bitrate setting. 

* To update the maximum bitrate setting during playback, create a new `PTABRControlParameters` instance and set it on the player instance.
* You can update the maximum bitrate setting during playback only on iOS 8.0 and later. For earlier versions, the `maxBitrate` value that was set before content playback started is used.



