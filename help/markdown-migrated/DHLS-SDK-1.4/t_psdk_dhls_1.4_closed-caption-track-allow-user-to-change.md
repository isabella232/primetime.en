---
description: This is an example of how to create a button that allows a user to select a closed-caption track.
seo-description: This is an example of how to create a button that allows a user to select a closed-caption track.
seo-title: Example: Allow users to change the caption track
title: Example: Allow users to change the caption track
---

# Example: Allow users to change the caption track

>1. Define a drop-down list.
>   ```
>   &lt;s:DropDownList id="ccTracksList" width="85" 
>    dataProvider="{_ccTracks}" 
>    change="onCCTrackChange(event)" 
>    prompt="CC"/&gt;
>   ```
>   
>   
>1. Define a bindable array of closed caption tracks.
>   ```
>   [Bindable] private var _ccTracks:ArrayCollection = 
>    new ArrayCollection(); // active tracks 
>   
>   ```
>   
>   
>1. Set up listeners.
>   
>   ```
>   player.addEventListener(MediaPlayerItemEvent.ITEM_CREATED, onItemCreated); 
>   player.addEventListener(MediaPlayerItemEvent.CAPTIONS_UPDATED, onCaptionUpdated);
>   ```
>   
>   To remove the listeners from your destruction code:
>   ```
>   player.removeEventListener(MediaPlayerItemEvent.ITEM_CREATED, onItemCreated); 
>   player.removeEventListener(MediaPlayerItemEvent.CAPTIONS_UPDATED, onCaptionUpdated);
>   ```
>   
>   
>   
>1. Create and update the list when a user makes a choice from the list.
>   ```
>   private function onCCTrackChange(event:IndexChangeEvent):void { 
>    var ccTrackIndex:int = event.newIndex; 
>    var ccTracks:Vector.&lt;ClosedCaptionsTrack&gt; = 
>    _player.currentItem.closedCaptionsTracks; 
>    if (ccTrackIndex == 0) { 
>    _player.ccVisibility = MediaPlayer.INVISIBLE; 
>    } 
>    else if (ccTrackIndex &lt;= _ccTracks.length) { 
>    var index:Number = findFromActiveIndex(ccTracks, ccTrackIndex - 1); 
>    _player.currentItem.selectClosedCaptionsTrack(ccTracks[index]); 
>    _player.ccVisibility = MediaPlayer.VISIBLE; 
>    } 
>   } 
>    
>   private function findFromActiveIndex(ccTracks:Vector.&lt;ClosedCaptionsTrack&gt;, 
>    ccTrackIndex:int):Number { 
>    var count:Number = 0; 
>    for each (var ccTrack:ClosedCaptionsTrack in ccTracks) { 
>    if (count &lt; ccTrackIndex) 
>    count = count + 1; 
>    else 
>    return count; 
>    } 
>    return -1; 
>   } 
>    
>   private function onItemCreated(event:MediaPlayerItemEvent):void { 
>    ... (you are likely to need more code here for other reasons) 
>    updateCCTracks(_player.currentItem.closedCaptionsTracks); 
>   } 
>    
>   private function onCaptionUpdated(event:MediaPlayerItemEvent):void { 
>    ... (you are likely to need more code here for other reasons) 
>    updateCCTracks(_player.currentItem.closedCaptionsTracks, 
>    (_player.ccVisibility == MediaPlayer.VISIBLE) ? 
>    _player.currentItem.selectedClosedCaptionsTrack : null); 
>   } 
>    
>   private function updateCCTracks(tracks:Vector.&lt;ClosedCaptionsTrack&gt;, 
>    selectedTrack:ClosedCaptionsTrack = null):void { 
>    _ccTracks.removeAll(); 
>    
>    _ccTracks.addItem( 
>    { 
>    "label": "CC off", 
>    "data": "cc-off" 
>    } 
>    ); 
>    
>    var selectedIndex:int = 0; 
>    for each (var ccTrack:ClosedCaptionsTrack in tracks) { 
>    _ccTracks.addItem( 
>    { 
>    "label": ccTrack.name, 
>    "data": ccTrack.name 
>    } 
>    ); 
>    if (selectedTrack &amp;&amp; ccTrack.name == selectedTrack.name &amp;&amp; 
>    ccTrack.language == selectedTrack.language &amp;&amp; 
>    ccTrack.serviceType == selectedTrack.serviceType) { 
>    selectedIndex = _ccTracks.length - 1; 
>    } 
>    } 
>    
>    var hasCC:Boolean = _ccTracks.length &gt; 0; 
>    ccTracksList.enabled = hasCC; 
>    ccTracksList.mouseEnabled = hasCC; 
>    ccTracksList.selectedIndex = selectedIndex; 
>   } 
>   
>   ```
>   
>   
>   
