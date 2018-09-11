---
description: When an entire playlist is missing, for example, when the M3U8 file that is specified in a top-level manifest file does not download, TVSDK attempts to recover. If it cannot be recovered, your application determines the next step.
seo-description: When an entire playlist is missing, for example, when the M3U8 file that is specified in a top-level manifest file does not download, TVSDK attempts to recover. If it cannot be recovered, your application determines the next step.
seo-title: Missing playlist failover
title: Missing playlist failover
uuid: f40b8943-ea94-49b2-abf6-d8bfdaf5c60a
index: y
internal: n
snippet: y
translate: y
---

# Missing playlist failover

When an entire playlist is missing, for example, when the M3U8 file that is specified in a top-level manifest file does not download, TVSDK attempts to recover. If it cannot be recovered, your application determines the next step.

If the playlist that is associated with the middle-resolution bit rate is missing, TVSDK searches for a variant playlist at the same resolution. If it finds the same resolution, TVSDK starts downloading the variant playlist and the segments from the matching position. If the player does not find the same resolution playlist, it will try to cycle through other bitrate playlists and their variants. An immediately lower bitrate is the first choice, then its variant, and so on. If all of the lower bitrate playlists and their variants are exhausted in the attempt to find a valid playlist, TVSDK will go to the top bitrate and count down from there. If a valid playlist cannot be found, the process fails, and the player moves to the ERROR state. 

Your application can determine how to handle this situation. For example, you might want to close the player activity and direct the user to the catalog activity. The event of interest is the `STATUS_CHANGED` event, and the corresponding callback is the `onStatusChanged` method. Here is code that monitors whether the player changes its internal status to `ERROR`: 

```
java... 
case ERROR: 
getActivity().finish(); // this is where we close the current activity (the Player activity) 
break; 
...
```
