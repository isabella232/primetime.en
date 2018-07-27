---
description: Event handlers allow to respond to events.
seo-description: Event handlers allow to respond to events.
seo-title: Implement event listeners and callbacks
title: Implement event listeners and callbacks
uuid: fa708050-7e92-4353-8eda-d53eee6dd784
index: n
internal: n
snippet: y
translate: y
---

# Implement event listeners and callbacks

When an event occurs,  <!-- PH element: phrases/primetime-sdk-name --> 's event mechanism calls your registered event handler and passes the event information to the handler.
<!-- PH element: phrases/primetime-sdk-name --> defines listeners as public internal interfaces in the `MediaPlayer` interface. 
Your application must implement event listeners for  <!-- PH element: phrases/primetime-sdk-name --> events that affect your application.
For a complete list of the events for video analytics, see [Track Core Video Playback](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/c_vhl_track-core-vid-playback.html). 

>1. Determine for which events your application must listen.
>    
>    * **Required events**: Listen for all playback events. 
>      >[!IMPORTANT]
>      >
>      >The playback event `onStateChanged` provides the player state, including errors. Any of the states might affect your player's next step. 

>    * **Other events**: Optional, depending on your application. For example, if you incorporate advertising in your playback, implement the `AdPlaybackEventListener` callbacks. 

>    
>1. Implement event listeners for each event.
>   <!-- PH element: phrases/primetime-sdk-name --> returns parameter values to your event-listener callbacks. These values, provide relevant information about the event that you can use in your listeners to perform appropriate actions.>
>   `MediaPlayer.EventListener` lists all the callback interfaces. Each interface displays the callback name and parameters that are returned for each event.>

>    
>       ```
>       java>       MediaPlayer.PlaybackEventListener.onStateChanged(
>         MediaPlayer.PlayerState state, MediaPlayerNotification notification)
>       ```
>1. Register your callback listeners with the `MediaPlayer` object by using `MediaPlayer.addEventListener`.

>    
>       ```
>       java>       mediaPlayer.addEventListener(MediaPlayer.Event.PLAYBACK, 
>         new MediaPlayer.PlaybackEventListener() {
>           @Override
>           public void onStateChanged(
>               MediaPlayer.PlayerState state, 
>               MediaPlayerNotification notification) {...}
>       }
>       ```
