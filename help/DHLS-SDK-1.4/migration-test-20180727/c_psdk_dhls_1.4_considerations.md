---
description: To use most effectively, you should consider certain details of its operation and follow certain best practices.
seo-description: To use most effectively, you should consider certain details of its operation and follow certain best practices.
seo-title: Considerations and best practices
title: Considerations and best practices
uuid: fd1f69b8-8372-488b-8faf-ec70f7cfb345
index: n
internal: n
snippet: y
translate: y
---

# Considerations and best practices


## Considerations {#section_tvsdk_considerations}

Remember the following information when using  <!-- PH element: phrases/primetime-sdk-name --> :
* Adobe Primetime does not work on emulators or simulators. You must use real devices for testing.

* Playback is supported only for HTTP Live Streaming (HLS) content.
* Main video content can be multiplexed, where video and audio streams are in the same rendition, or nonmultiplexed, where video and audio streams are in separate renditions.
* The  <!-- PH element: phrases/primetime-sdk-name --> API is implemented in ActionScript.
* Video playback requires the Adobe Video Engine (AVE). This affects how and when media resources can be accessed: 
    * Closed captioning is supported to the extent provided by the AVE.
    * Depending on encoder precision, the actual encoded media duration might differ from the durations that are recorded in the stream resource manifest. There is no reliable way to resynchronize between the ideal virtual timeline and the actual playout timeline. Progress tracking of the stream playback for ad management and Video Analytics must use the actual playout time, so reporting and user interface behavior might not precisely track the media and advertisement content.

    * The incoming user agent name for all HTTP requests from  <!-- PH element: phrases/primetime-sdk-name --> on this platform is assigned the following string pattern:    
      ```
      "Adobe Flash Player"
      ```




## Best practices {#section_tvsdk_best_practices}

Here are recommended practices for  <!-- PH element: phrases/primetime-sdk-name --> :
* Use HLS version 3.0 or above for program content.
* For  <!-- PH element: phrases/primetime-sdk-name --> 1.4 for DHLS, lazy ad loading is enabled by default.For content with no pre-roll or mid-roll, you can use `AdvertisingMetadata.delayAdLoading` to accelerate content loading even more. 


