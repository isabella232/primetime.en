---
description: Alternate audio allows you to switch among available audio tracks for a video track. Users can select their preferred language track when the video is played.
seo-description: Alternate audio allows you to switch among available audio tracks for a video track. Users can select their preferred language track when the video is played.
seo-title: Alternate audio
title: Alternate audio
---

# Alternate audio

<a id="section_E4F9DC28A2944BD08B4190A7F98A8365"></a>

When  creates the `codeph  MediaPlayerItem` instance for the current video, it creates an `codeph  AudioTrack` item for each available audio track. The item contains a `codeph  name` property, which is a string that typically contains a user-recognizable description of the language of that track. The item also contains information about whether to use that track by default. When it is time to play the video, you can ask for a list of available audio tracks, optionally allow the user select a track, and set the video to play with the selected track.

>[!TIP]
>
>Although rare, if an additional audio track becomes available after creates the `codeph  MediaPlayerItem`,  fires a `codeph  MediaPlayerItem.AUDIO_TRACK_UPDATED` event.


## Added APIs {#section_87C42C30BA8C4F58A2DAB7CE07FCD3DE}

The following APIs have been added to support alternate audio:

`codeph  **hasAlternateAudio**`

If the specified media has an alternate audio track, other than default track, this boolean function returns `codeph  true`. If there is no alternate audio track, the function returns `codeph  false`.
```java
boolean hasAlternateAudio();
```

** `codeph  getAudioTracks`**

This function returns list of all the current available audio tracks in a specified media.
```java
List&lt;AudioTrack&gt; getAudioTracks();
```

`codeph  **getSelectedAudioTrack**`

This function that returns the currently selected alternate audio track and properties such as language. The auto-selection of track can also be extracted.
```java
AudioTrack getSelectedAudioTrack();
```

`codeph  **selectAudioTrack**`

This function selects an alternate audio track to play.
```java
void selectAudioTrack(AudioTrack audioTrack);
```

For example:
```java
private void onPrepared() { 
 // Select the AA track in PREPARED State 
 boolean hasAlternateAudio = _mediaPlayer.getCurrentItem().hasAlternateAudio(); 
 if(hasAlternateAudio) { 
 AudioTrack selectedAudioTrack = 
 _mediaPlayer.getCurrentItem().getSelectedAudioTrack(); 
 
 if (selectedAudioTrack == null) { 
 // Selecting default audio track 
 // If index is 1 it will select alternate audio track 
 selectedAudioTrack = _mediaPlayer.getCurrentItem().getAudioTracks().get(0); 
 } 
 } 
 _mediaPlayer.getCurrentItem().selectAudioTrack(selectedAudioTrack); 
} 

```
