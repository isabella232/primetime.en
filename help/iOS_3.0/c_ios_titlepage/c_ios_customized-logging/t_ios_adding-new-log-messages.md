---
seo-title: Adding new log messages
title: Adding new log messages
uuid: 2598906d-0e03-41d8-af68-2a53690f3c8b
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
