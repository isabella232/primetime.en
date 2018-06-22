---
seo-title: Implement IPlaybackConfig
title: Implement IPlaybackConfig
---

# Implement IPlaybackConfig

To configure buffer parameters, you can implement [ `apiname  IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html) [ `apiname  IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/dhls/asdoc/com/adobe/primetime/reference/configuration/IPlaybackConfig.html) `apiname  getInitBufferTime()` and `apiname  getBufferTime()`.

The reference implementation uses SharedPreferences for the configuration source.

To see how the reference implementation reads the configuration information from SharedPreferences using [ `apiname  IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html) [ `apiname  IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/dhls/asdoc/com/adobe/primetime/reference/configuration/IPlaybackConfig.html) `apiname  getInitBufferTime()` and `apiname  getBufferTime()`, refer to the `codeph  ConfigProvider.java` file:
```java
/** 
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

>   1.
>   
>   
