---
description: You can set the policy for pre-roll ad playback in the reference player.
seo-description: You can set the policy for pre-roll ad playback in the reference player.
seo-title: DVR with ad insertion and pre-roll support
title: DVR with ad insertion and pre-roll support
uuid: 0abc7865-0c26-4b11-9a8e-74af6a58f918
index: n
internal: n
snippet: y
translate: y
---

# DVR with ad insertion and pre-roll support

The KEEP policy states that the pre-roll ad will be inserted into the playback window and remain in the stream during the entire playback experience. If the user seeks back into the playback window, they will see the same pre-roll ad again.
The REMOVE policy states that the pre-roll ad will be removed from the window after it has played or when the user seeks to a point past the ad. The default behavior for the  reference implementation is REMOVE. 
The policy is set in the CustomAdBreakPolicySelector class.

```
javapublic class CustomAdBreakPolicySelector implements AdBreakPolicySelector { 
    private MediaPlayerItem _mediaPlayerItem; 
    public CustomAdBreakPolicySelector(MediaPlayerItem _mediaPlayerItem) { 
        this._mediaPlayerItem = _mediaPlayerItem; 
  
    } 
    @Override 
    public AdBreakPolicy selectPolicyFor(AdBreak adBreak, PlacementInformation placementInformation) { 
        if (placementInformation.getType().equals(PlacementInformation.Type.PRE_ROLL) &amp;&amp; _mediaPlayerItem.isLive()) 
 { 
            return AdBreakPolicy.REMOVE; 
        } 
        return AdBreakPolicy.KEEP; 
    } 
}
```

```
<draft-comment>
  Need code sample for Desktop. There is no CustomAdBreakPolicySelector class for Desktop. 
</draft-comment>
```
