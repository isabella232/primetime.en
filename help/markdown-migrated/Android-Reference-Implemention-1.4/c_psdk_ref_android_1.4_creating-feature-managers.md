---
description: features are driven by configuration and implemented through the MediaPlayer.
seo-description: features are driven by configuration and implemented through the MediaPlayer.
seo-title: Creating feature managers by passing configuration information to the MediaPlayer
title: Creating feature managers by passing configuration information to the MediaPlayer
---

# Creating feature managers by passing configuration information to the MediaPlayer


* Configuration is the list of specific settings for the feature, such as initial bit rate of ABR control and default closed captioning visibility.
  Feature managers need to get the configurations in order to determine the feature behavior.
  
  In the Primetime reference implementation, the configuration is stored in shared preferences, but you can store the configuration in whatever way makes sense for your environment.
  
  
* `codeph  MediaPlayer` is the  media player object that contains the video resource.
  Feature managers register  event listeners to this player object, retrieve data from the playback session and trigger  features to the playback session.
  
  

Each feature has a corresponding configuration interface. For example, `codeph  CCManager` uses `codeph  ICCConfig` to retrieve the configuration. `codeph  ICCConfig` contains methods to get the configuration information related to closed captioning only.

The following example shows the `filepath  ICCConfig.java` file, configured to receive information about closed caption visibility, font style, and font edge from the `codeph  MediaPlayer`:

```java
// Constructor of CCManager 
 
<b>public CCManager(ICCConfig ccConfig, MediaPlayer mediaPlayer) {...}</b> 
 
// ICCConfig methods 
 
<b>public interface ICCConfig {</b> 
 
 /** 
 * Get the closed captioning visibility config 
 * 
 * @return true if visibility is set to true, false otherwise 
 */ 
 
<b> public boolean getCCVisibility();</b> 
 
 /** 
 * Get the closed captioning font style 
 * 
 * @return TextFormat.Font object represents font style 
 */ 
 
<b>public TextFormat.Font getCCFont();</b> 
 
 
 /** 
 * Get the closed captioning font edge 
 * 
 * @return TextFormat.FontEdge represents of font edge 
 */ 
 
<b>public TextFormat.FontEdge getCCFontEdge();</b> 
... 
}
```
An application that uses a  feature can create its feature manager with a configuration provider and a `codeph  MediaPlayer` object. For example:

```java
// This application needs to use the advertising workflow feature 
AdsManager adsManager = new AdsManagerOn();
```
Feature manager configuration API docs: [ Javadoc ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/package-summary.html)

