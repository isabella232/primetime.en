---
description: For some low bit-rate playback rates, the , by default, switches to the audio-only stream and the playback appears frozen. You can configure the player so that it never encounters a situation where it switches to audio-only.
seo-description: For some low bit-rate playback rates, the , by default, switches to the audio-only stream and the playback appears frozen. You can configure the player so that it never encounters a situation where it switches to audio-only.
seo-title: Configure for low bit rates
title: Configure for low bit rates
---

# Configure for low bit rates

>1. Implement the [IPlaybackConfig](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html) interface:
>* Ensure that [getABRMinBitRate](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html#getABRMinBitRate()) is higher than the audio-only bit rate (higher than 64000).
>* Ensure that [isABRControlEnabled](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html#isABRControlEnabled()) is on.
>   
>   
>   
