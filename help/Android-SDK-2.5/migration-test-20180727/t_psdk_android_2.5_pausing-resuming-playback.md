---
description: When a user clicks an ad, your application should pause playback of the main video content.
seo-description: When a user clicks an ad, your application should pause playback of the main video content.
seo-title: Pause and resume playback
title: Pause and resume playback
uuid: bc16e446-976f-4feb-8657-b64785976163
index: n
internal: n
snippet: y
translate: y
---

# Pause and resume playback


>1. Override the ` onPause` and ` onResume` from Android Activity.
>
>   ```
>   java>   @Override 
>   public void onResume() { 
>       super.onResume(); 
>       requestAudioFocus(); 
>       if (_lastKnownStatus == MediaPlayerStatus.PAUSED) { 
>           _mediaPlayer.play(); 
>       } 
>   } 
>   ... 
>    
>   @Override 
>   public void onPause() { 
>       super.onPause(); 
>       if (_mediaPlayer != null) { 
>           if (_mediaPlayer.getStatus() == MediaPlayerStatus.PLAYING || 
>             _mediaPlayer.getStatus() == MediaPlayerStatus.PAUSED) { 
>               _savedPlayerStatus = _mediaPlayer.getStatus(); 
>               _lastKnownTime = _mediaPlayer.getCurrentTime(); 
>           } 
>           if (_mediaPlayer.getStatus() == MediaPlayerStatus.PLAYING) { 
>               _mediaPlayer.pause(); 
>               _lastKnownStatus = MediaPlayerStatus.PAUSED; 
>           } 
>       } 
>   } 
>   abandonAudioFocus(); 
>   
>   ```
>
