---
description: You can obtain a description of the timeline associated with the currently selected item being played by . This is most useful when your application displays a custom scrub-bar control in which the content sections that correspond to ad content are identified.
seo-description: You can obtain a description of the timeline associated with the currently selected item being played by . This is most useful when your application displays a custom scrub-bar control in which the content sections that correspond to ad content are identified.
seo-title: Inspect the playback timeline
title: Inspect the playback timeline
uuid: 895a475e-9b1f-46bb-a902-2d19532231d0
index: n
internal: n
snippet: y
translate: y
---

# Inspect the playback timeline

Here is an example implementation as seen in the following screen shot.  ![](images/inspect-playback.jpg) 

>1. Access the ` Timeline` object in the ` MediaPlayer` using the ` getTimeline()` method.
>   The ` Timeline` class encapsulates the information that is related to the contents of the timeline that is associated with the media item that is currently loaded by the ` MediaPlayer` instance. The ` Timeline` class provides access to a read-only view of the underlying timeline. The ` Timeline` class provides a getter method that provides an iterator through a list of ` TimelineMarker` objects. 
>
>1. Iterate through the list of ` TimelineMarkers` and use the returned information to implement your timeline.
>       A ` TimelineMarker` object contains two pieces of information: 
>    
>    * Position of the marker on the timeline (in milliseconds)
>    * Duration of the marker on the timeline (in milliseconds)
>    
>1. Listen for the ` MediaPlayerEvent.TIMELINE_UPDATED` event on the ` MediaPlayer` instance, and implement the ` TimelineUpdatedEventListener.onTimelineUpdated()` callback.
>   The ` Timeline` object can inform your application about changes that might occur in the playback timeline by calling your ` OnTimelineUpdated` listener.>
