---
description: Event handlers enable you to respond to TVSDK events.
seo-description: Event handlers enable you to respond to TVSDK events.
seo-title: Implement event listeners and callbacks
title: Implement event listeners and callbacks
uuid: 4dbdf453-af13-42f4-b280-18c15b07a6c6
index: y
internal: n
snippet: y
translate: y
---

# Implement event listeners and callbacks

Event handlers enable you to respond to TVSDK events.

When an event occurs, TVSDK's event mechanism calls your registered event handler, passing it the event information. 

TVSDK defines listeners as public internal interfaces inside the `MediaPlayer` interface. 

Your application must implement event listeners for any TVSDK events that affect your application. 

1. Determine which events your application must listen for.

    
    * Required events: Listen for all playback events. 
      >[!IMPORTANT]
      >
      >Listen for the status change event, which occurs when the player's status changes in ways that you need to know. The information it provides includes errors that might affect what your player can do next.
    
    * For other events, depending on your application, see  events-summary .    
    
    
    
1. Implement and add an event listener for each event.

   For most events TVSDK passes arguments to the event listeners. Such values provide information about the event that can help you decide what to do next.

   The `MediaPlayerEvent` enumeration lists all the events that `MediaPlayer` dispatches. For more information, see  events-summary .

   `mPlayer``MediaPlayer`
   ```
   java   mPlayer.addEventListener(MediaPlayerEvent.STATUS_CHANGED, new StatusChangeEventListener() { 
       @Override 
       public void onStatusChanged(MediaPlayerStatusChangeEvent event) { 
           event.getMetadata(); 
           if (event.getMetadata() != null) {/* Do something */} 
           if (event.getStatus() == MediaPlayerStatus.IDLE) {/* Do something */} 
           else if (event.getStatus() == MediaPlayerStatus.INITIALIZED) {/* Do something */} 
           else if (event.getStatus() == MediaPlayerStatus.PREPARED) {/* Do something */} 
       } 
   }); 
   
   ```
