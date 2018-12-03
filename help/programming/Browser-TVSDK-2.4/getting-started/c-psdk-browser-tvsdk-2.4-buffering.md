---
description: You can configure visuals to notify the user that content is buffering.
seo-description: You can configure visuals to notify the user that content is buffering.
seo-title: Buffering
title: Buffering
uuid: be3a631f-ab17-4857-b5bd-cd01b99257d1
index: y
internal: n
snippet: y
---

# Buffering{#buffering}

You can configure visuals to notify the user that content is buffering.

Listen for `AdobePSDK.PSDKEventType.BUFFERING_BEGIN` and `AdobePSDK.PSDKEventType.BUFFERING_END` events. For example: 

```js
player.addEventListener(AdobePSDK.PSDKEventType.BUFFERING_BEGIN,  
                        function (event) { 
                            buffering = true; 
                            // add buffering layer 
                        }); 
  
player.addEventListener(AdobePSDK.PSDKEventType.BUFFERING_END,  
                        function (event) { 
                           buffering = false; 
                           // remove buffering layer 
                        });
```

The UI Framework provides default buffering overlay behavior implementation, which can be extended as shown below: 

```js
// Using UI Framework 
function myBufferingOverlayBehavior (element, configuration, player, localize, baseLog) { 
    return ptp.bufferingOverlayBehavior(element, configuration, player, localize, baseLog); 
} 
var playerWrapper = ptp.videoPlayer('.videoDiv', { 
    player: { 
        mediaResource:'Specify Resource URL', 
        bufferingOverlay: { 
            behavior: myBufferingOverlayBehavior, 
            classNames: 'ptp-buffering-overlay my_buffering_overlay_bar' 
        } 
    } 
 
}); 

```

Here is what the result DOM looks like: 

```
<div id=" videoDiv" class="ptp-root-element"> 
<div name="videoPlayer" value="videoPlayer" class="ptp-main-video-div-style"> 
<div name="bufferingOverlay" value="bufferingOverlay" class="ptp-buffering-overlay my_buffering_overlay_bar'"></div> 
</div> 
</div> 

```

