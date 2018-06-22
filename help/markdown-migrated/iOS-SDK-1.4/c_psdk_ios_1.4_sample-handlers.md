---
seo-title: Sample handlers for notifications
title: Sample handlers for notifications
---

# Sample handlers for notifications

The following code snippets illustrate some of the ways you can use notifications.

Fetch the `codeph  PTAdBreak` instance using `codeph  PTMediaPlayerAdBreakKey`:
```
 - (void) onMediaPlayerAdBreakStarted:(NSNotification *) notification { 
 // Fetch the PTAdBreak instance using PTMediaPlayerAdBreakKey 
 PTAdBreak *adBreak = [notification.userInfo objectForKey:PTMediaPlayerAdBreakKey]; 
 ... 
 ... 
} 

```

Set `codeph  subtitlesOptions` and `codeph  audioOptions`:

```
 - (void) onMediaPlayerItemMediaSelectionOptionsAvailable:(NSNotification \*) notification { 
 //SubtitlesOptions and audioOptions are set and accessible now. 
 NSArray* subtitlesOptions = self.player.currentItem.subtitlesOptions; 
 NSArray* audioOp tions = self.player.currentItem.audioOptions; 
 ... 
 ... 
} 

```
Fetch the `codeph  PTAd` instance using `codeph  PTMediaPlayerAdKey`:

```
 - (void) onMediaPlayerAdPlayStarted:(NSNotification \*) notification { 
 // Fetch the PTAdinstance using PTMediaPlayerAdKey 
 PTAd *ad = [notification.userInfo objectForKey:PTMediaPlayerAdKey]; 
 ... 
 ... 
} 

```
