---
description: You can configure custom tag names in globally with the PTSDKConfig class. Q: Double-check whether iOS also has the stream-based method. There's no MediaPlayerItemConfig in Android.
seo-description: You can configure custom tag names in globally with the PTSDKConfig class. Q: Double-check whether iOS also has the stream-based method. There's no MediaPlayerItemConfig in Android.
seo-title: Config class methods for tags
title: Config class methods for tags
uuid: d4524f21-fba9-4923-8741-cc0e747f9bc3
index: n
internal: n
snippet: y
translate: y
---

# Config class methods for tags

 <!-- PH element: phrases/primetime-sdk-name --> applies the global configuration automatically to any media stream that does not specify a stream-specific configuration.
`PTSDKConfig` exposes these methods to manage the custom tags: 

| **Subscribe to specific custom tags** |
|---|
| `subscribedTags`  |Retrieves the current list of subscribed tags. |
| `setSubscribedTags`  |Sets the list of subscribed tags that will be exposed to the application. |
| **Customize the ad tags used by the default opportunity detector** |
|  `adTags`  |Retrieves the current list of ad tags. |
|  `setAdTags`  |Sets the list of ad tags that will be used by default opportunity generator. |

Remember the following: 
* The setter methods do not allow the tags parameter to contain null values.
* The custom tag name must contain the # prefix. For example, #EXT-X-ASSET is a correct custom tag name, but EXT-X-ASSET is incorrect.

* You cannot change the configuration after the media stream has been loaded.

