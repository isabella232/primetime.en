---
description: The MediaPlayer provides methods to set and get the initial buffering time and playback buffering time.
seo-description: The MediaPlayer provides methods to set and get the initial buffering time and playback buffering time.
seo-title: Set buffering times
title: Set buffering times
---

# Set buffering times

>[!TIP]
>
>If you do not set the buffer control parameters before beginning playback, the media player defaults to 2 seconds for the initial buffer and 30 seconds for the ongoing playback buffer time.
>1. Set up the `codeph  BufferControlParameters` object, which encapsulates the initial buffer time and playback buffer time control parameters.
>   This class provides the following factory methods:
>* To set the initial buffer time equal to the play buffer time:
>  ```
>  public static BufferControlParameters createSimple(long bufferTime)
>  ```
>  
>* To set the initial and play buffer times:
>  ```
>  public static BufferControlParameters createDual( 
>   long initialBuffer, 
>   long bufferTime)
>  ```
>  
>   
>   If the parameters are not valid, these methods throw `codeph  MediaPlayerException` with error code `codeph  PSDKErrorCode.INVALID_ARGUMENT`, such as when the following conditions are met:
>* The initial buffer time is less than zero.
>* The initial buffer time is greater than the buffer time.
>   
>   
>   
>1. To set the buffer parameters values, use this `codeph  MediaPlayer` method:
>   ```java
>   void setBufferControlParameters(BufferControlParameters params)
>   ```
>   
>   
>1. To get the current buffer parameter values, use this `codeph  MediaPlayer` method:
>   ```java
>   >   BufferControlParameters getBufferControlParameters() 
>   
>   ```
>   
>   
>   
