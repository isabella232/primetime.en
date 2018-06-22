---
description: You can choose a custom starting point for when to enter a DVR stream instead of the default behavior of entering the DVR stream at the beginning using the ConfigProvider class.
seo-description: You can choose a custom starting point for when to enter a DVR stream instead of the default behavior of entering the DVR stream at the beginning using the ConfigProvider class.
seo-title: Choosing a custom starting point for DVR
title: Choosing a custom starting point for DVR
---

# Choosing a custom starting point for DVR

To set the start time through the [ConfigProvider](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/ConfigProvider.html) class:

>1. Enable [isCustomPositionPrefEnabled()](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/ConfigProvider.html#isCustomPositionPrefEnabled()).
>   
>1. Set the start time in `codeph [retrieveStartTimePref()](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html#iretrieveStartTimePref()).`
>   
>1. Check that the custom start position is enabled.
>   
>   
