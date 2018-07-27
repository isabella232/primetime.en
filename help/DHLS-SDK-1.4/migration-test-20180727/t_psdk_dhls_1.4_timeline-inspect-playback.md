---
description: You can obtain a description of the timeline associated with the currently selected item being played by . This is most useful when your application displays a custom scrub-bar control in which the content sections that correspond to ad content are identified.
seo-description: You can obtain a description of the timeline associated with the currently selected item being played by . This is most useful when your application displays a custom scrub-bar control in which the content sections that correspond to ad content are identified.
seo-title: Inspect the playback timeline
title: Inspect the playback timeline
uuid: f5cfd19a-83a5-4edf-b7f9-d05a6d1c5534
index: n
internal: n
snippet: y
translate: y
---

# Inspect the playback timeline

Here is an example implementation as seen in the following screen shot.  ![](images/inspect-playback.jpg) 

>1. Access the ` Timeline` object in the ` MediaPlayer` using the ` get` method.
>   The ` Timeline` class encapsulates the information that is related to the contents of the timeline that is associated with the media item that is currently loaded by the ` MediaPlayer` instance. The ` Timeline` class provides access to a read-only view of the underlying timeline. The ` Timeline` class provides a getter method for obtaining all placed ` TimelineMarker` objects. 
>
>1. Iterate through the list of ` TimelineMarkers` and use the returned information to implement your timeline.
>       A ` TimelineMarker` object contains two pieces of information: 
>    
>    * Position of the marker on the timeline (in milliseconds)
>    * Duration of the marker on the timeline (in milliseconds)
>    
