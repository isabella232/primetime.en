---
description: The MediaPlayer provides methods to set and get the initial buffering time and playback buffering time.
seo-description: The MediaPlayer provides methods to set and get the initial buffering time and playback buffering time.
seo-title: Set buffering times
title: Set buffering times
uuid: d93d79e8-db03-4d1f-a6f0-19d4aece0843
index: y
internal: n
snippet: y
translate: y
---

# Set buffering times

The MediaPlayer provides methods to set and get the initial buffering time and playback buffering time.


>[!TIP]
>
>If you do not set the buffer control parameters before beginning playback, the media player defaults to 2 seconds for the initial buffer and 30 seconds for the ongoing playback buffer time.

1. Set up the `BufferControlParameters` object, which encapsulates the initial buffer time and playback buffer time control parameters.

       This class provides the following factory methods:     
    * To set the initial buffer time equal to the play buffer time:     
      ```
      public static BufferControlParameters createSimple(long bufferTime)
      ```
    
    * To set the initial and play buffer times:     
      ```
      public static BufferControlParameters createDual( 
        long initialBuffer,  
        long bufferTime)
      ```
    
    
    

    
       If the parameters are not valid, these methods throw `MediaPlayerException` with error code `PSDKErrorCode.INVALID_ARGUMENT`, such as when the following conditions are met:     
    * The initial buffer time is less than zero.    
    * The initial buffer time is greater than the buffer time.    
    
    

    
1. To set the buffer parameters values, use this `MediaPlayer` method:

   ```
   java   void setBufferControlParameters(BufferControlParameters params)
   ```

1. To get the current buffer parameter values, use this `MediaPlayer` method:

   ```
   java      BufferControlParameters getBufferControlParameters()  
   
   ```

For example, to set the initial buffer to 5 seconds and the playback buffer time to 30 seconds: 

```
javamediaPlayer.setBufferControlParameters(BufferControlParameters.createDual(5000, 30000));
```
