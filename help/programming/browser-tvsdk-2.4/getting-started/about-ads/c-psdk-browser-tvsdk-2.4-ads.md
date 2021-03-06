---
description: When content is playing, Browser TVSDK can display ads and pass information about ads when creating the MediaResource object.
seo-description: When content is playing, Browser TVSDK can display ads and pass information about ads when creating the MediaResource object.
seo-title: Ads
title: Ads
uuid: 9a5e8c83-18ce-41e8-9cb1-fdc9da903faf
---

# Overview {#ads-overview}

When content is playing, Browser TVSDK can display ads and pass information about ads when creating the MediaResource object.

You can optionally call the `prepareToPlay` function after you receive `AdobePSDK.MediaPlayerStatus.INITIALIZED`. 

```js
function onStatusChange (event) { 
   switch (event.status) { 
     case AdobePSDK.MediaPlayerStatus.INITIALIZED: 
        player.prepareToPlay(AdobePSDK.MediaPlayer.LIVE_POINT); 
        break; 
     case AdobePSDK.MediaPlayerStatus.PREPARED: 
        player.play(); 
        break; 
   } 
} 
 
var auditudeSettings     = new AdobePSDK.AuditudeSettings(); 
auditudeSettings.domain  = "sample_auditude_domain"; 
auditudeSettings.mediaId = "sample_media_id"; 
auditudeSettings.zoneId  = "sample_zone_id"; 
 
// event handler 
player.addEventListener(AdobePSDK.PSDKEventType.STATUS_CHANGED, onStatusChange); 
 
var mediaResource = new AdobePSDK.MediaResource(resourceUrl, resourceType, auditudeSettings, false);
```

Browser TVSDK also provides the following ad-specific events that you can use in your event handlers to prevent content from fast forwarding when ads are playing:

* `AdobePSDK.PSDKEventType.AD_BREAK_STARTED` 
* `AdobePSDK.PSDKEventType.AD_BREAK_COMPLETED` 
* `AdobePSDK.PSDKEventType.AD_STARTED` 
* `AdobePSDK.PSDKEventType.AD_COMPLETED`

To see this working in the UI Framework, specify ad settings in configuration as follows: 

```js
// Using UI Framework 
var playerWrapper = ptp.videoPlayer('.videoDiv', { 
    player: { 
        mediaResource: { 
 
            resourceUrl:'Specify Resource Url', 
 
            auditudeSettings: { 
                validMimeTypes: ["application/x-mpeURL"], 
                domain: "Sample_auditude_domain", 
                mediaId:"sample_media_id", 
                zoneID:"sample_zone_id", 
                creativeRepackagingEnabled:true 
            } 
        } 
    } 
}; 

```

For more information about the required `AuditudeSettings`, see [Ad insertion metadata](../../ad-insertion/ad-insertion-metadata/c-psdk-browser-tvsdk-2.4-ad-insertion-metadata.md).
