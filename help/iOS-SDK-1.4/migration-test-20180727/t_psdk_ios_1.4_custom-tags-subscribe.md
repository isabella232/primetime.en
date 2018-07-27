---
description: prepares PTTimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.
seo-description: prepares PTTimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.
seo-title: Subscribe to custom tags
title: Subscribe to custom tags
uuid: 3bca029d-8abb-4c78-8264-2a1ca1a930a9
index: n
internal: n
snippet: y
translate: y
---

# Subscribe to custom tags

Before the playback starts, you must subscribe to the tags.
To be notified about custom tags in HLS manifests:

>1. Set the custom ad tag names globally by passing an array that contains the custom tags to ` setSubscribedTags` in ` PTSDKConfig`.

>   >[!IMPORTANT]
>   >
>   >You must include the ` #` prefix when working with HLS streams. 
>   For example: >
>   ```
>   NSArray *customHLSTags = [NSArray arrayWithObjects:@"#EXT-OATCLS-SCTE35",@"#EXT_CUSTOM_TAG2",nil]; 
>   [PTSDKConfig  setSubscribedTags:customHLSTags];
>   ```

>
