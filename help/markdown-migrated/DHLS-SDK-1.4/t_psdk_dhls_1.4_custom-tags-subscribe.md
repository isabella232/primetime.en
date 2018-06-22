---
description: prepares TimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.
seo-description: prepares TimedMetadata objects for subscribed tags each time these objects are encountered in the content manifest.
seo-title: Subscribe to custom tags
title: Subscribe to custom tags
---

# Subscribe to custom tags

Before the playback starts, you must subscribe to the tags.

To subscribe to tags, assign a vector that contains the custom tag names to the `codeph  subscribedTags` property. If you need to also change the ad tags used by the default opportunity generator, then assign a vector that contains the custom ad tag names to the `codeph  adTags` property.

To be notified about custom tags in HLS manifests:

>1. Set the custom ad tag names globally by assigning a vector that contains the custom tags to `codeph  subscribeTags` in `codeph  MediaPlayerItemConfig`.
>   >[!IMPORTANT]
>   >
>   >You must include the`codeph  #` prefix when working with HLS streams.
>   For example:
>   ```
>   var subscribedTags:Vector.&lt;String&gt; = new Vector.&lt;String&gt;(); 
>   subscribedTags.push("#EXT-X-ASSET"); 
>   subscribedTags.push("#EXT-X-AD"); 
>   PSDKConfig.subscribedTags = subscribedTags;
>   ```
>   
>   
>   
>1. To globally change the ad tags that are used by the default opportunity generator, assign a vector that contains the custom ad tag names to the `codeph  adTags` property in `codeph  PSDKConfig`.
>       
>       ```
>       var adTags:Vector.&lt;String&gt; = new Vector.&lt;String&gt;(); 
>       adTags.push("#EXT-X-AD"); 
>       PSDKConfig.adTags = adTags; 
>       
>       ```
>       
>   
>1. To have all the global settings take effect, replace the current resource.
>       
>       ```
>       player.replaceCurrentResource(mediaResource);
>       ```
>       
>   
>1. To set the subscribed tag names for a stream, if needed:
>   >1. Create a media player item configuration.
>   >   >[!TIP]
>   >   >
>   >   >The easiest way is to create a default media player item configuration.
>   >   
>   >   
>   >1. Assign a vector that contains the custom tags to `codeph  subscribeTags` in `codeph  MediaPlayerItemConfig`.
>   >   
>   >   
>       
>       ```
>       var mediaPlayerItemConfig:MediaPlayerItemConfig = 
>        new DefaultMediaPlayerItemConfig(); 
>        
>       var subscribedTags:Vector.&lt;String&gt; = new Vector.&lt;String&gt;(); 
>       subscribedTags.push("#EXT-X-ASSET"); 
>       subscribedTags.push("#EXT-X-AD"); 
>       mediaPlayerItemConfig.subscribeTags = subscribedTags;
>       ```
>       
>   
>1. To change the ad tags that are used by the default opportunity generator in the specified stream, assign a vector that contains the custom ad tag names to the `codeph  adTags` property in `codeph  mediaPlayerItemConfig`
>       
>       ```
>       var adTags:Vector.&lt;String&gt; = new Vector.&lt;String&gt;(); 
>       adTags.push("#EXT-X-AD"); 
>       mediaPlayerItemConfig.adTags = adTags;
>       ```
>       
>   
>1. To have the changes for the stream take effect, when loading the media stream, use the media player item configuration.
>       
>       ```
>       player.replaceCurrentResource(mediaResource, mediaPlayerItemConfig);
>       ```
>       
>   
>   
