---
description: When your playback includes advertising, dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-description: When your playback includes advertising, dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-title: Order of advertising events
title: Order of advertising events
uuid: b0be33a8-4cf9-4e4c-ad41-402b0da4fcd4
index: n
internal: n
snippet: y
translate: y
---

# Order of advertising events


<a id="section_6A672A7FBF6C496E8FF83DDF61511996"></a>

When playing ads, the order of events is: 
* ` AdPlaybackEventListener.onAdBreakStart`
* The following are dispatched for every ad in the ad break: 
    * ` AdPlaybackEventListener.onAdStart`
    * ` AdPlaybackEventListener.onAdProgress` (multiple times during an ad's playback)
    * ` AdPlaybackEventListener.onAdClick` (for each click)
    * ` AdPlaybackEventListener.onAdStart`

* ` AdPlaybackEventListener.onAdBreakComplete`

The following example shows a typical progression of ad playback events:

```
javamediaPlayer.addEventListener(MediaPlayer.Event.AD_PLAYBACK,  
  new MediaPlayer.AdPlaybackEventListener() { 
    @Override  
    public void onAdBreakStart(AdBreak adBreak) { ... } 
    @Override 
    public void onAdStart(AdBreak adBreak, Ad ad) { ... } 
    @Override 
    public void onAdProgress(AdBreak adBreak, Ad ad, int percentage) { ... }  
    @Override 
    public void onAdComplete(AdBreak adBreak, Ad ad) { ... } 
    @Override 
    public void onAdBreakComplete(AdBreak adBreak) { ... } 
    @Override 
    public void onAdClick(AdBreak adBreak, Ad ad, AdClick adClick) { ... } 
});
```

<a id="section_69E3CCBC57BB48399799876E83908348"></a>

When playing ads, the order of events is: 
* ` AdPlaybackEventListener.onAdBreakStart`
* The following are dispatched for every ad in the ad break: 
    * ` AdPlaybackEventListener.onAdStart`
    * ` AdPlaybackEventListener.onAdProgress` (multiple times during an ad's playback)
    * ` AdPlaybackEventListener.onAdClick` (for each click)
    * ` AdPlaybackEventListener.onAdStart`

* ` AdPlaybackEventListener.onAdBreakComplete`

The following example shows a typical progression of ad playback events:

```
javamediaPlayer.addEventListener(MediaPlayer.Event.AD_PLAYBACK,  
  new MediaPlayer.AdPlaybackEventListener(){ 
    @Override  
    public void onAdBreakStart(AdBreak adBreak) { ... } 
    @Override 
    public void onAdStart(AdBreak adBreak, Ad ad) { ... } 
    @Override 
    public void onAdProgress(AdBreak adBreak, Ad ad, int percentage) { ... }  
    @Override 
    public void onAdComplete(AdBreak adBreak, Ad ad) { ... } 
    @Override 
    public void onAdBreakComplete(AdBreak adBreak) { ... } 
    @Override 
    public void onAdClick(AdBreak adBreak, Ad ad, AdClick adClick) { ... } 
});
```
