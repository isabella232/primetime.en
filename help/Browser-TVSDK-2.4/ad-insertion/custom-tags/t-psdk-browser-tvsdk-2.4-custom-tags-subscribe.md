---
description: Browser TVSDK prepares TimedMetadata objects for subscribed tags each time these objects are encountered in the Media Presentation Description (MPD) file.
seo-description: Browser TVSDK prepares TimedMetadata objects for subscribed tags each time these objects are encountered in the Media Presentation Description (MPD) file.
seo-title: Subscribe to custom ad tags
title: Subscribe to custom ad tags
uuid: 456a1b88-3b8f-46f4-b2d1-6ffa137b150f
index: y
internal: n
snippet: y
---

# Subscribe to custom ad tags{#subscribe-to-custom-ad-tags}

Browser TVSDK prepares TimedMetadata objects for subscribed tags each time these objects are encountered in the Media Presentation Description (MPD) file.

You must subscribe to the tags before playback starts. 
To subscribe to tags, set a vector that contains the custom tag names to the `subscribedTags` property. If you also need to change the ad tags used by the default opportunity generator, set a vector that contains the custom ad tag names to the `adTags` property.

To subscribe to custom tags: 

1. Create a new media player item configuration.

   ```js
   var mediaPlayerItemConfig = new AdobePSDK.MediPlayerItemConfig();
   ```

1. Create an empty string-vector.

   ```js
   var subscribeTags = [];
   ```

1. Add the custom tag names to this vector.

   >[!IMPORTANT]
   >
   >If you are dealing with HLS streams, remember to include the `#` prefix.

   ```js
   subscribeTags.push("urn:mpeg:dash:event:2012"); 
   subscribeTags.push("urn:com:adobe:dpi:simple:2015"); 
   
   ```

1. Assign the updated vector to the `mediaPlayerItemConfig.subscribeTags` property.

   ```js
   mediaPlayerItemConfig.subscribeTags = subscribeTags;
   ```

1. Create an empty string-vector.

   ```js
   var adTags= [];
   ```

1. Add the custom ad tag name to this vector.

   ```js
   adTags.push("urn:com:adobe:dpi:simple:2015");
   ```

1. Assign the updated vector to the `mediaPlayerItemConfig.adTags` property.

   ```js
   mediaPlayerItemConfig.adTags = adTags;
   ```

1. Use the media player item configuration when loading the media stream.

   ```js
   player.replaceCurrentResource(mediaResource,mediaPlayerItemConfig);
   ```
