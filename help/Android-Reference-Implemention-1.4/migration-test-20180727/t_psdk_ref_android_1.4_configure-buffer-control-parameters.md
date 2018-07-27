---
description: You can set different buffering policies in the , consisting of the initial buffer time and the playback buffer time, depending on your needs, such as the device, the operating system, or the network conditions.
seo-description: You can set different buffering policies in the , consisting of the initial buffer time and the playback buffer time, depending on your needs, such as the device, the operating system, or the network conditions.
seo-title: Configure buffer control parameters
title: Configure buffer control parameters
uuid: ff60e76c-579a-48f3-8130-7de3988bc46c
index: n
internal: n
snippet: y
translate: y
---

# Configure buffer control parameters

When the media player buffer reaches the initial buffer time, playback begins.
This improves the start-up time because the player does not wait for the entire buffer to fill before starting playback. Instead, after a few seconds are buffered, playback begins. While the video is being rendered,  continues to buffer new fragments until it is has buffered the amount that is specified by the playback buffer time. If the current buffer length drops below the playback buffer time, the player will download additional fragments. Once the current buffer length is above the playback buffer time by a few seconds,  will stop downloading fragments. 
To configure buffer parameters, implement [  <!-- APINAME - Required Post Migration Cleanup --> ` IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html)  <!-- APINAME - Required Post Migration Cleanup --> ` getInitBufferTime()` and  <!-- APINAME - Required Post Migration Cleanup --> ` getBufferTime()`. 
The reference implementation uses SharedPreferences for the configuration source.
To see how the reference implementation reads the configuration information from SharedPreferences using [  <!-- APINAME - Required Post Migration Cleanup --> ` IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html) ` getInitBufferTime()` and ` getBufferTime()`, refer to the ` ConfigProvider.java` file: 
```
java/** 
 * {inheritDoc} 
 */ 
@Override 
public long getInitBufferTime() { 
    long initBufferTime = PreferencesUtils.getLongPreference(preferences, 
                          PlaybackManager.SETTINGS_BUFFER_INIT, 
                          PlaybackManager.DEFAULT_INIT_BUFFER); 
    return initBufferTime; 
} 
 
/** 
 * {inheritDoc} 
 */ 
@Override 
public long getBufferTime() { 
    long playBufferTime = PreferencesUtils.getLongPreference(preferences, 
                          PlaybackManager.SETTINGS_BUFFER_TIME, 
                          PlaybackManager.DEFAULT_BUFFER_TIME); 
    return playBufferTime; 
} 

```

