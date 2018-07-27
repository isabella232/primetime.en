---
seo-title: Implement IPlaybackConfig
title: Implement IPlaybackConfig
uuid: 09ad203f-5ad3-4df0-9ae3-c2f134d09f60
index: n
internal: n
snippet: y
translate: y
---

# Implement IPlaybackConfig

To configure buffer parameters, you can implement [  <!-- APINAME - Required Post Migration Cleanup --> ` IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html) [  <!-- APINAME - Required Post Migration Cleanup --> ` IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/dhls/asdoc/com/adobe/primetime/reference/configuration/IPlaybackConfig.html)  <!-- APINAME - Required Post Migration Cleanup --> ` getInitBufferTime()` and  <!-- APINAME - Required Post Migration Cleanup --> ` getBufferTime()`. 
The reference implementation uses SharedPreferences for the configuration source.
To see how the reference implementation reads the configuration information from SharedPreferences using [  <!-- APINAME - Required Post Migration Cleanup --> ` IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html) [  <!-- APINAME - Required Post Migration Cleanup --> ` IPlaybackConfig` ](http://help.adobe.com/en_US/primetime/reference_implementation/dhls/asdoc/com/adobe/primetime/reference/configuration/IPlaybackConfig.html)  <!-- APINAME - Required Post Migration Cleanup --> ` getInitBufferTime()` and  <!-- APINAME - Required Post Migration Cleanup --> ` getBufferTime()`, refer to the ` ConfigProvider.java` file: 
```
java /** 
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


>1.
