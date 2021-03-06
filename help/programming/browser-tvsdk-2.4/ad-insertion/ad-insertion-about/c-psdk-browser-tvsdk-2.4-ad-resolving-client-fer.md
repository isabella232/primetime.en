---
description: Full Event Replay (FER) content is a live stream converted to VOD by adding the #EXT-X-ENDLIST tag to the end of the manifest file. The stream retains its ad cue markers.
seo-description: Full Event Replay (FER) content is a live stream converted to VOD by adding the #EXT-X-ENDLIST tag to the end of the manifest file. The stream retains its ad cue markers.
seo-title: FER ad resolving and insertion
title: FER ad resolving and insertion
uuid: 85da0e92-17fe-4001-a53c-085dadd09756
---

# FER ad resolving and insertion{#fer-ad-resolving-and-insertion}

Full Event Replay (FER) content is a live stream converted to VOD by adding the #EXT-X-ENDLIST tag to the end of the manifest file. The stream retains its ad cue markers.

Browser TVSDK treats a FER stream as VOD, so by default the ad signaling mode is `SERVER_MAP`. However, since the stream retains its ad cue markers, you can set the ad signaling mode to `MANIFEST_CUES`, which lets you use the ad cue markers for ad insertion.

To turn on ad insertion using cue markers for a FER stream: 

```js
var config = new AdobePSDK.MediaPlayerItemConfig(); 
config.adSignalingMode = AdobePSDK.AdSignalingMode.MANIFEST_CUES; 
player.replaceCurrentResource(mediaResource, config);
```

FER ad resolving and insertion behavior is similar to live ad resolving and insertion. Browser TVSDK does the following:

1. Inserts any pre-roll ads at the beginning of the content. 
1. Resolves ads specified by the cue points defined in the manifest. 
1. Replaces parts of the main content with ad breaks of the same duration 
1. Re-computes the virtual timeline, if necessary.

**Restriction:** Browser TVSDK supports only HLS FER streams playback. Also, MP4 mid-roll ads are not supported with FER streams. 
