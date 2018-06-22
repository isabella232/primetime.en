---
description: You can select a track from a list of currently available closed-caption tracks. This becomes the current track, which is displayed when visibility is on. Some tracks might not be available initially, so listen for the event that indicates that more have become available.
seo-description: You can select a track from a list of currently available closed-caption tracks. This becomes the current track, which is displayed when visibility is on. Some tracks might not be available initially, so listen for the event that indicates that more have become available.
seo-title: Select a current caption track from among available tracks
title: Select a current caption track from among available tracks
---

# Select a current caption track from among available tracks

>[!TIP]
>
>Closed captions are always enabled. All default closed-caption tracks are considered to be present. Default tracks (such as CC1-CC4, CS1-CS6) are enumerated in`codeph  ClosedCaptionsTrack.DefaultCCTypes`. When playback begins,  looks for activity on any of these channels. If it finds activity, it sets the `codeph  isActive` method for that track and dispatches the `codeph  MediaPlayer.PlaybackEventListener.onUpdated` event.
>1. Wait for the media player to be in least the PREPARED state.
>   
>1. Listen for these events:
>    * `codeph  MediaPlayer.PlaybackEventListener.onStateChanged with state MediaPlayer.PlayerState.INITIALIZED`: The initial list of closed-caption tracks is available
>   
>1. Get a list of all currently available closed-caption tracks.
>   For example:
>   ```java
>   List&lt;ClosedCaptionsTrack&gt; ccTracks = 
>    mediaPlayer.getCurrentItem().getClosedCaptionsTracks();
>   ```
>   
>   
>1. Select an available track to be the current track.
>   For example:
>   ```java
>   // Select the initial CC track. 
>   for (int i = 0; i &lt; ccTracks.size(); i++) { 
>    ClosedCaptionsTrack track = ccTracks.get(i); 
>    if (track.getName().equals(INITIAL_CC_TRACK)) { 
>    
<b>mediaPlayer.getCurrentItem().selectClosedCaptionsTrack(track);</b> 
>    selectedClosedCaptionsIndex = i; 
>    } 
>   }
>   ```
>   
>   
>1. Implement a listener for the event that indicates that more tracks are available. When  dispatches the event, retrieve the current list of available tracks.
>   Retrieve the list each time that the event occurs to ensure that you always have the most current list.
>   
>   
