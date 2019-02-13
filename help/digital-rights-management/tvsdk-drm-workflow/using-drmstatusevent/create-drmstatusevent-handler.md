---
seo-title: Create a DRMStatusEvent handler
title: Create a DRMStatusEvent handler
uuid: 64f539d9-344c-4372-88b8-c8d098af9dd8
---

# Create a DRMStatusEvent handler{#create-a-drmstatusevent-handler}

The following example creates an event handler that outputs the DRM content status information for the Primetime object that originated the event. 

Add an event handler to a Primetime object that points to protected content:

   ```
   function drmStatusEventHandler(event:DRMStatusEvent):void { trace(event); } 
   ```

