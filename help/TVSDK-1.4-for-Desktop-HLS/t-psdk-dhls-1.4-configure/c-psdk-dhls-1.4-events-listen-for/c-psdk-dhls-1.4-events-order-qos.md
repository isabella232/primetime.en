---
description: TVSDK dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering and seeking events.
seo-description: TVSDK dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering and seeking events.
seo-title: QoS events
title: QoS events
uuid: 36138eaf-1b66-4c48-9e36-508b889be738
index: y
internal: n
snippet: y
---

# QoS events{#qos-events}

TVSDK dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering and seeking events.

The following example shows a typical progression of these events: 

```
// For buffering 
mediaPlayer.addEventListener(BufferEvent.BUFFERING_BEGIN, onBufferingBegin); 
private function onBufferingBegin(event:BufferEvent):void { ... } 
 
mediaPlayer.addEventListener(BufferEvent.BUFFERING_END, onBufferingCompleted); 
private function onBufferingCompleted(event:BufferEvent):void { ... } 
 
// For seeking 
mediaPlayer.addEventListener(SeekEvent.SEEK_BEGIN, onSeekBegin); 
private function onSeekBegin(event:SeekEvent):void { ... } 
 
mediaPlayer.addEventListener(SeekEvent.SEEK_COMPLETED, onSeekCompleted); 
private function onSeekCompleted(event:SeekEvent):void { ... } 
 
...  SeekEvent.SEEK_POSITION_ADJUSTED...  //if the desired 
// seek position is modified by the current advertising policies 

```

