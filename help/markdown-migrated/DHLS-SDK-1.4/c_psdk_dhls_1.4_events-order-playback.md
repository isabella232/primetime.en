---
description: dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-description: dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-title: Order of playback events
title: Order of playback events
---

# Order of playback events

<a id="section_6E34A6C7936245D88DEB3315DA64598B"></a>

The following examples show the order of some events that include playback events.

* When successfully loading a media resource through `codeph  MediaPlayer.replaceCurrentResource`, the order of events is:
    * `codeph  MediaPlayerStatusChangeEvent.STATUS_CHANGED` with status `codeph  MediaPlayerStatus.INITIALIZING`
    * `codeph  MediaPlayerItemEvent.ITEM_CREATED`
    * `codeph  MediaPlayerStatusChangeEvent.STATUS_CHANGED` with status `codeph  MediaPlayerStatus.INITIALIZED`
  
* When preparing for playback through `codeph  MediaPlayer.prepareToPlay`, the order of events is:
    * `codeph  MediaPlayerStatusChangeEvent.STATUS_CHANGED` with status `codeph  MediaPlayerStatus.PREPARING`
    * `codeph  TimelineEvent.TIMELINE_UPDATED` if ads were inserted
    * `codeph  MediaPlayerStatusChangeEvent.STATUS_CHANGED` with status `codeph  MediaPlayerStatus.PREPARED`
  
* For live/linear streams, during playback as the playback window advances and additional opportunities are resolved, the order of events is:
    * `codeph  MediaPlayerItemEvent.ITEM_UPDATED`
    * `codeph  TimelineEvent.TIMELINE_UPDATED` if ads were inserted
  
<a id="section_76C13548AF934868B70757CA5489E516"></a>

The following example shows a typical progression of events:

```
mediaPlayer.addEventListener(MediaPlayerItemEvent.ITEM_CREATED, onItemCreated); 
public function onItemCreated(event:MediaPlayerItemEvent):void { 
 var item:MediaPlayerItem = event.item; 
 ... 
} 
mediaPlayer.addEventListener(MediaPlayerItemEvent.ITEM_UPDATED, onItemUpdated); 
public function onItemUpdated(event:MediaPlayerItemEvent):void { 
 var item:MediaPlayerItem = event.item; 
 ... 
} 
mediaPlayer.addEventListener(MediaPlayerStatusChangeEvent.STATUS_CHANGED, 
 onStatusChanged); 
public function onStatusChanged(event:MediaPlayerStatusChangeEvent):void { 
 switch(event.status){ 
 case MediaPlayerStatus.INITIALIZING: 
 case MediaPlayerStatus.INITIALIZED: 
 ... 
 } 
 ... 
} 
mediaPlayer.addEventListener(TimeChangeEvent.TIME_CHANGED, onTimeChanged); 
public function onTimeChanged(event:TimeChangeEvent):void { 
 var timeInMilliseconds:Number = event.time; 
 ... 
}
```
