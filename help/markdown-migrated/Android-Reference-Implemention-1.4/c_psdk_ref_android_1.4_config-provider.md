---
description: The ConfigProvider class gets the configuration for the media player. You must implement the configuration interface so the feature managers can read the configuration information.
seo-description: The ConfigProvider class gets the configuration for the media player. You must implement the configuration interface so the feature managers can read the configuration information.
seo-title: ConfigProvider
title: ConfigProvider
---

# ConfigProvider

You use the [ConfigProvider](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/ConfigProvider.html) class to implement the `codeph ICCConfig`, `codeph IAAConfig`, `codeph IPlaybackConfig`, `codeph IAdConfig`, and `codeph IQosConfig` configuration interfaces so that the feature managers can read the configurations. For example, the `codeph ICCConfig` is the interface for the `codeph CCManager` configuration. The configuration files receive the configuration parameters from the JSON configuration file.

The `codeph ConfigProvider.java` file is an example of Adobe's implementation of the configuration interfaces. It reads the settings from `codeph SharedPreferences`, where the configuration is stored. You can store your configuration in any way that works for your organization. The config implementation provides a wrapper for your configuration source.

