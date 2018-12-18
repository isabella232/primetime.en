---
seo-title: Add new log messages
title: Add new log messages
uuid: b180f859-9714-445a-ad30-926bea9a88f7
index: y
internal: n
snippet: y
---

# Add new log messages{#add-new-log-messages}

 To register to listen to logs: 
1. Create a new `PTLogEntry` and add it to `thePTLogFactory`:

   You can manually instantiate a `PTLogEntry` and add it to the `PTLogFactory` shared instance or use one of the macros to accomplish the same task.

   Here is an example of logging using the `PTLogDebug` macro:

<a id="example_F014436E1686468F941F4EBD1A21B18E"></a>

```
// The following line creates an instance of PTLogEntry with type PTLogEntryDebug, 
// tag "DEBUG_PLAYBACK", and message "Playback has started". 
// Then the PTLogEntry is automatically added to the PTLogFactory  
 
PTLogDebug(@"[DEBUG_PLAYBACK] Playback has started");
```

