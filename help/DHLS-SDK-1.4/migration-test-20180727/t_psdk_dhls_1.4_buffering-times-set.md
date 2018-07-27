---
description: The MediaPlayer provides methods to set and get the initial buffering time and playback buffering time.
seo-description: The MediaPlayer provides methods to set and get the initial buffering time and playback buffering time.
seo-title: Set buffering times
title: Set buffering times
uuid: 6584e735-6c45-4707-9800-da7deb9c06d8
index: n
internal: n
snippet: y
translate: y
---

# Set buffering times


>[!TIP]
>
>If you do not set the buffer control parameters before beginning playback, the media player defaults to 2 seconds for the initial buffer and 30 seconds for the ongoing playback buffer time.


>1. Set up the ` BufferControlParameters` object, which encapsulates the initial buffer time and playback buffer time control parameters:
>       This class provides the following factory methods: >    
>    * To set the initial buffer time equal to the play buffer time: >    
>      ```
>      createSimple(bufferTime:uint):BufferControlParameters
>      ```

>    * To set both the initial and play buffer times: >    
>      ```
>      createDual(initialBufferTime:uint, playbackBufferTime:uint):BufferControlParameters 
>      
>      ```


>       These methods throw an ` IllegalArgumentException` if the parameters are not valid, such as when: >    
>    * The initial buffer time is less than zero.
>    * The initial buffer time is greater than the buffer time.

>    
>1. To set the buffer parameter values, use this ` MediaPlayer` method:
>
>   ```
>   public function set bufferControlParameters(value:BufferControlParameters):void
>   ```
>
>1. To get the current buffer parameter values, use this ` MediaPlayer` method:
>
>   ```
>   public function get bufferControlParameters():BufferControlParameters
>   ```
>
