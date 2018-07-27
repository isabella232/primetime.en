---
description: null
seo-description: null
seo-title: Configure adaptive bit rates
title: Configure adaptive bit rates
uuid: 7cc3d075-57ae-47b7-ab24-0ca9394b8483
index: n
internal: n
snippet: y
translate: y
---

# Configure adaptive bit rates

To configure  <!-- PH element: phrases/primetime-sdk-name --> adaptive bit-rate parameters:

>1. Configure an instance of ` PTABRControlParameters` to set the initial, minimum, and maximum bit-rate settings.
>   The default values are displayed in the following code snippet, but your application can set any integer value for each of these parameters. 
>   >[!IMPORTANT]
>   >
>   >Specify the bit-rate settings in bits-per-second (bps).
>
>   ```
>   // ARC (add autorelease for non-ARC) 
>   PTABRControlParameters *abrMetaData =  
>       [[PTABRControlParameters alloc] init];  
>    
>   abrMetaData.initialBitRate = -1; 
>   abrMetaData.minBitRate = 0; 
>   abrMetaData.maxBitRate = INT_MAX;
>   ```

>
>1. Update your ` PTMediaPlayer` instance with the configured ` PTABRControlParameters` instance.
>
>   ```
>   // assuming self.player is the PTMediaPlayer instance 
>   self.player.abrControlParameters = abrMetaData;
>   ```
>
