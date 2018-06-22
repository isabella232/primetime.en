---
description: When a user clicks an ad, your application should pause playback of the main video content.
seo-description: When a user clicks an ad, your application should pause playback of the main video content.
seo-title: Pause and resume playback
title: Pause and resume playback
---

# Pause and resume playback

>1. Override the `codeph  onPause` and `codeph  onResume` from the Android Activity.
>   ```java
>   @Override 
>   public void onResume() { 
>    super.onResume(); 
>    requestAudioFocus(); 
>    if (_lastKnownStatus == MediaPlayer.PlayerState.PAUSED) { 
>    _mediaPlayer.play(); 
>    } 
>   } 
>   ... 
>    
>   @Override 
>   public void onPause() { 
>    super.onPause(); 
>    if (_mediaPlayer != null) { 
>    if (_mediaPlayer.getStatus() == MediaPlayer.PlayerState.PLAYING || 
>    _mediaPlayer.getStatus() == MediaPlayer.PlayerState.PAUSED) { 
>    _savedPlayerState = _mediaPlayer.getStatus(); 
>    _lastKnownTime = _mediaPlayer.getCurrentTime(); 
>    } 
>    if (_mediaPlayer.getStatus() == MediaPlayer.PlayerState.PLAYING) { 
>    _mediaPlayer.pause(); 
>    _lastKnownStatus = MediaPlayer.PlayerState.PAUSED; 
>    } 
>    } 
>   } 
>    
>   abandonAudioFocus(); 
>   
>   ```
>   
>   
>   
