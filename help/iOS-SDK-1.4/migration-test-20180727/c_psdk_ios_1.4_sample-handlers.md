---
seo-title: Sample handlers for notifications
title: Sample handlers for notifications
uuid: ed7446f0-87d9-4bef-ab34-3f8dac446d6b
index: n
internal: n
snippet: y
translate: y
---

# Sample handlers for notifications

The following code snippets illustrate some of the ways you can use notifications.
Fetch the ` PTAdBreak` instance using ` PTMediaPlayerAdBreakKey`: 
```
 - (void) onMediaPlayerAdBreakStarted:(NSNotification *) notification { 
   // Fetch the PTAdBreak instance using PTMediaPlayerAdBreakKey 
   PTAdBreak *adBreak = [notification.userInfo objectForKey:PTMediaPlayerAdBreakKey]; 
   ... 
   ... 
} 

```

Set ` subtitlesOptions` and ` audioOptions`: 

```
 - (void) onMediaPlayerItemMediaSelectionOptionsAvailable:(NSNotification \*) notification { 
   //SubtitlesOptions and audioOptions are set and accessible now. 
   NSArray* subtitlesOptions = self.player.currentItem.subtitlesOptions;  
   NSArray* audioOp tions = self.player.currentItem.audioOptions; 
   ... 
   ... 
} 

```
Fetch the ` PTAd` instance using ` PTMediaPlayerAdKey`: 

```
 - (void) onMediaPlayerAdPlayStarted:(NSNotification \*)  notification { 
   // Fetch the PTAdinstance using PTMediaPlayerAdKey 
   PTAd *ad = [notification.userInfo objectForKey:PTMediaPlayerAdKey]; 
   ... 
   ... 
} 

```
