---
description: When your playback includes advertising, dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-description: When your playback includes advertising, dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-title: Order of advertising events
title: Order of advertising events
---

# Order of advertising events

<a id="section_6A672A7FBF6C496E8FF83DDF61511996"></a>

When playing ads, the order of events is:
* `codeph  AdPlaybackEventListener.onAdBreakStart`
* The following are dispatched for every ad in the ad break:
    * `codeph  AdPlaybackEventListener.onAdStart`
    * `codeph  AdPlaybackEventListener.onAdProgress` (multiple times during an ad's playback)
    * `codeph  AdPlaybackEventListener.onAdClick` (for each click)
    * `codeph  AdPlaybackEventListener.onAdStart`
  
* `codeph  AdPlaybackEventListener.onAdBreakComplete`

The following example shows a typical progression of ad playback events:

```java
mediaPlayer.addEventListener(MediaPlayer.Event.AD_PLAYBACK, 
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
* `codeph  AdPlaybackEventListener.onAdBreakStart`
* The following are dispatched for every ad in the ad break:
    * `codeph  AdPlaybackEventListener.onAdStart`
    * `codeph  AdPlaybackEventListener.onAdProgress` (multiple times during an ad's playback)
    * `codeph  AdPlaybackEventListener.onAdClick` (for each click)
    * `codeph  AdPlaybackEventListener.onAdStart`
  
* `codeph  AdPlaybackEventListener.onAdBreakComplete`

The following example shows a typical progression of ad playback events:

```java
mediaPlayer.addEventListener(MediaPlayer.Event.AD_PLAYBACK, 
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
