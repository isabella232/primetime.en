---
description: When your playback includes advertising, dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-description: When your playback includes advertising, dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-title: Order of advertising events
title: Order of advertising events
---

# Order of advertising events

<a id="section_14D78B5608DD4639B166F4872F6FBC62"></a>

When playing ads, the order of events is:
* `codeph  MediaPlayerEvent.AD_START`
* The following are dispatched for every ad in the ad break:
    * `codeph  MediaPlayerEvent.AD_START`
    * `codeph  MediaPlayerEvent.AD_PROGRESS` (multiple times)
    * `codeph  MediaPlayerEvent.AD_CLICK` (for each click)
    * `codeph  MediaPlayerEvent.AD_COMPLETE`
  
* `codeph  MediaPlayerEvent.AD_BREAK_COMPLETE`

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
mediaPlayer.addEventListener(MediaPlayerEvent.AD_START, new 
 MediaPlayer.AdStartedEventListener(){ 
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
