---
description: dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-description: dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-title: Order of playback events
title: Order of playback events
uuid: 676afb04-c66a-4f60-a7e7-53d8e931b6c6
index: n
internal: n
snippet: y
translate: y
---

# Order of playback events


<a id="section_E70BFC1D44EE4BAD8FA2A875552EFA0D"></a>

The following examples show the order of some events that include playback events.

* When successfully loading a media resource through ` MediaPlayer.replaceCurrentItem`, the order of events is: 
    * ` MediaPlayer.PlaybackEventListener.onStateChanged` with state ` MediaPlayer.PlayerState.INITIALIZING`
    * ` MediaPlayer.PlaybackEventListener.onStateChanged` with state ` MediaPlayer.PlayerState.INITIALIZED`

  >[!TIP]
  >
  >Load your media resource on the main thread. If you load a media resource on a background thread, this operation or subsequent <!-- PH element: phrases/primetime-sdk-name --> operations, or both, might throw an error (for example, ` IllegalStateException`) and exit. 

* When preparing for playback through ` MediaPlayer.prepareToPlay`, the order of events is: 
    * ` MediaPlayer.PlaybackEventListener.onStateChanged` with state ` MediaPlayer.PlayerState.PREPARING`
    * ` MediaPlayer.PlaybackEventListener.onTimelineUpdated` if ads were inserted
    * ` MediaPlayer.PlaybackEventListener.onStateChanged` with state ` MediaPlayer.PlayerState.PREPARED`

* For live/linear streams, during playback as the playback window advances and additional opportunities are resolved, the order of events is: 
    * ` MediaPlayer.PlaybackEventListener.onUpdated`
    * ` MediaPlayer.PlaybackEventListener.onTimelineUpdated` if ads were inserted
    * ` MediaPlayerItemEvent.ITEM_UPDATED`
    * ` TimelineEvent.TIMELINE_UPDATED` if ads were inserted

The following example shows a typical progression of events:

```
javamediaPlayer.addEventListener(MediaPlayer.Event.PLAYBACK,  
  new MediaPlayer.PlaybackEventListener() { 
    @Override 
    public void onPrepared() {...} 
    @Override 
    public void onUpdated() {...} 
    @Override 
    public void onPlayStart() {...} 
    @Override 
    public void onPlayComplete() {...} 
    @Override 
    public void onSizeAvailable(long height, long width) {...} 
    @Override 
    public void onStateChanged(MediaPlayer.PlayerState state,  
      MediaPlayerNotification notification) {...} 
});
```

<a id="section_76C13548AF934868B70757CA5489E516"></a>

The following example shows a typical progression of events:

```
javamediaPlayer.addEventListener(MediaPlayer.Event.PLAYBACK,  
  new MediaPlayer.PlaybackEventListener() { 
    @Override 
    public void onPrepared() {...} 
    @Override 
    public void onUpdated() {...} 
    @Override 
    public void onPlayStart() {...} 
    @Override 
    public void onPlayComplete() {...} 
    @Override 
    public void onSizeAvailable(long height, long width) {...} 
    @Override 
    public void onStateChanged(MediaPlayer.PlayerState state,  
      MediaPlayerNotification notification) {...} 
});
```
