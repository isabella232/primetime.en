---
seo-title: Create a DRMErrorEvent handler
title: Create a DRMErrorEvent handler
uuid: 267b0ece-5764-4772-b7d1-54f3840c792e
index: y
internal: n
snippet: y
---

# Create a DRMErrorEvent handler{#create-a-drmerrorevent-handler}

1. Create an event handler to process error events dispatched from Primetime when it encounters an error while trying to play protected content.

   Normally, when an application encounters an error, it performs any number of clean-up tasks. It then informs the user of the error and provides options for solving the problem. 

   ```
   private function drmErrorEventHandler(event:DRMErrorEvent):void {  
       trace(event.toString());  
   } 
   ```

