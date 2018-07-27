---
description: Event handlers enable you to respond to events.
seo-description: Event handlers enable you to respond to events.
seo-title: Implement event listeners and callbacks
title: Implement event listeners and callbacks
uuid: 7d31e5d4-d5b2-4b1b-9832-9cdb3bd3b884
index: n
internal: n
snippet: y
translate: y
---

# Implement event listeners and callbacks

When an event occurs,  <!-- PH element: phrases/primetime-sdk-name --> 's event mechanism calls your registered event handler, passing it the event information.
<!-- PH element: phrases/primetime-sdk-name --> defines listeners as public internal interfaces inside the ` MediaPlayer` interface. 
Your application must implement event listeners for any  <!-- PH element: phrases/primetime-sdk-name --> events that affect your application.

>1. Determine which events your application must listen for.
>    
>    * Required events: Listen for all playback events. 
>      >[!IMPORTANT]
>      >
>      >Listen for the status change event, which occurs when the player's status changes in ways that you need to know. The information it provides includes errors that might affect what your player can do next.

>    * For other events, depending on your application, see  events-summary .
>    
>1. Implement and add an event listener for each event.
>   For most events <!-- PH element: phrases/primetime-sdk-name --> passes arguments to the event listeners. Such values provide information about the event that can help you decide what to do next.>
>   The ` MediaPlayerEvent` enumeration lists all the events that ` MediaPlayer` dispatches. For more information, see  events-summary .>

>       ` mPlayer`` MediaPlayer`>    
>       ```
>       java>       mPlayer.addEventListener(MediaPlayerEvent.STATUS_CHANGED, new StatusChangeEventListener() { 
>           @Override 
>           public void onStatusChanged(MediaPlayerStatusChangeEvent event) { 
>               event.getMetadata(); 
>               if (event.getMetadata() != null) {/* Do something */} 
>               if (event.getStatus() == MediaPlayerStatus.IDLE) {/* Do something */} 
>               else if (event.getStatus() == MediaPlayerStatus.INITIALIZED) {/* Do something */} 
>               else if (event.getStatus() == MediaPlayerStatus.PREPARED) {/* Do something */} 
>           } 
>       }); 
>       
>       ```
