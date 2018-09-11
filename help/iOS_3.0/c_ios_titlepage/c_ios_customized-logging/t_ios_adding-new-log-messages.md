---
seo-title: Adding new log messages
title: Adding new log messages
uuid: 308a6be9-4ac6-4bca-89d1-c21f50e5e64d
index: y
internal: n
snippet: y
translate: y
---

# Adding new log messages

To register to listen to logs:
1. Create a new `PTLogEntry` and add it to `thePTLogFactory`:

   You can manually instantiate a `PTLogEntry` and add it to the `PTLogFactory` shared instance or use one of the macros to accomplish the same task. 


   Here is an example of logging using the `PTLogDebug` macro:

```
// The following line creates an instance of PTLogEntry with type PTLogEntryDebug, 
// tag "DEBUG_PLAYBACK", and message "Playback has started". 
// Then the PTLogEntry is automatically added to the PTLogFactory  
 
PTLogDebug(@"[DEBUG_PLAYBACK] Playback has started");
```
