---
seo-title: Create a DRMStatusEvent handler
title: Create a DRMStatusEvent handler
uuid: 093b52e0-5db5-49dd-8194-3518755d2e9b
index: y
internal: n
snippet: y
---

# Create a DRMStatusEvent handler{#create-a-drmstatusevent-handler}

The following example creates an event handler that outputs the DRM content status information for the Primetime object that originated the event. 

1. Add an event handler to a Primetime object that points to protected content:

   ```
   function drmStatusEventHandler(event:DRMStatusEvent):void { trace(event); } 
   ```

