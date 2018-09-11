---
description: TVSDK prepares PTTimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.
seo-description: TVSDK prepares PTTimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.
seo-title: Subscribe to custom tags
title: Subscribe to custom tags
uuid: 9e2b3186-90fc-4330-8c5f-f3b4614f2f7f
index: y
internal: n
snippet: y
translate: y
---

# Subscribe to custom tags

TVSDK prepares PTTimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.

Before the playback starts, you must subscribe to the tags. 
To be notified about custom tags in HLS manifests: 

1. Set the custom ad tag names globally by passing an array that contains the custom tags to `setSubscribedTags` in `PTSDKConfig`.


   >[!IMPORTANT]
   >
   >You must include the `#` prefix when working with HLS streams. 
   For example: 
   ```
   NSArray *customHLSTags = [NSArray arrayWithObjects:@"#EXT-OATCLS-SCTE35",@"#EXT_CUSTOM_TAG2",nil]; 
   [PTSDKConfig  setSubscribedTags:customHLSTags];
   ```


