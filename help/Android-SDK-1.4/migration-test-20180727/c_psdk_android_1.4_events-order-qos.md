---
description: dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering and seeking events.
seo-description: dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering and seeking events.
seo-title: QoS events
title: QoS events
uuid: 05a036ce-74ba-4667-8322-902a785b38b6
index: n
internal: n
snippet: y
translate: y
---

# QoS events

The following example shows a typical progression of these events: 
```
javamediaPlayer.addEventListener(MediaPlayer.Event.QOS,  
  new MediaPlayer.QOSEventListener(){ 
    //For buffering activity 
    @Override 
    public void onBufferStart() 
    @Override 
    public void onBufferComplete() 
    // For seeking 
    @Override 
    public void onSeekStart() 
    @Override 
    public void onSeekComplete(long adjustedTime) 
    @Override 
    public void onLoadComplete (MediaPlayerItem mediaplayeritem) 
    @Override 
    public void onLoadInfo(LoadInfo loadInfo) 
    @Override 
    public void onOperationFailed(MediaPlayerNotification.Warning warning) 
});
```

