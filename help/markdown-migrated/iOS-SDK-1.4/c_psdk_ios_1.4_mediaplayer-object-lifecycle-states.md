---
description: From the moment that you create the PTMediaPlayer instance to the moment when you terminate (reuse or remove) it, this instance completes a series of transitions from one status to another.
seo-description: From the moment that you create the PTMediaPlayer instance to the moment when you terminate (reuse or remove) it, this instance completes a series of transitions from one status to another.
seo-title: MediaPlayer object lifecycle
title: MediaPlayer object lifecycle
---

# MediaPlayer object lifecycle

Some operations are permitted only when the player is in a particular state. For example, calling `codeph play` in `codeph PTMediaPlayerStatusCreated` is not allowed. You can call this status only after the player reaches the `codeph PTMediaPlayerStatusReady` status.

To work with statuses:
* You can retrieve the current status of the MediaPlayer object with `codeph PTMediaPlayer.status`.
* The list of statuses is defined in `codeph PTMediaPlayerStatus`.

State-transition diagram for the lifecycle of a MediaPlayer instance:

<table id="table_426F0093E4214EA88CD72A7796B58DFD"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="1.41*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry">PTMediaPlayerStatus</th> 
    <th colname="col2" class="entry">Occurs when</th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p><span class="codeph">PTMediaPlayerStatusCreated</span> </p> </td> 
    <td colname="col2"> <p>Your application requested a new media player by calling <span class="codeph">playerWithMediaPlayerItem</span>. The newly created player is waiting for you to specify a media player item. This is the media player's initial status. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p> <span class="codeph">PTMediaPlayerStatusInitializing</span> </p> </td> 
    <td colname="col2"> <p>Your application calls <span class="codeph">PTMediaPlayer.replaceCurrentItemWithPlayerItem</span>, and the media player is loading. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><span class="codeph">PTMediaPlayerStatusInitialized</span> </p> </td> 
    <td colname="col2"> <p>
      <ph conkeyref="phrases/primetime-sdk-name" /> successfully set the media player item. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p> <span class="codeph">PTMediaPlayerStatusReady</span> </p> </td> 
    <td colname="col2"> <p>The content is prepared and ads have been inserted in the timeline, or the ad procedure failed. Buffering or playback can begin.</p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><span class="codeph">PTMediaPlayerStatusPlaying</span> </p> </td> 
    <td colname="col2"> <p>Your application has called <span class="codeph">play</span>, so 
      <ph conkeyref="phrases/primetime-sdk-name" /> is trying to play the video. Some buffering might occur before the video actually plays. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><span class="codeph">PTMediaPlayerStatusPaused</span> </p> </td> 
    <td colname="col2"> <p>As your application plays and pauses the media, the media player moves between this state and <span class="codeph">PTMediaPlayerStatusPlaying</span>. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><span class="codeph">PTMediaPlayerStatusCompleted</span> </p> </td> 
    <td colname="col2"> <p>The player reached the end of the stream, and playback has stopped.</p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><span class="codeph">PTMediaPlayerStatusStopped</span> </p> </td> 
    <td colname="col2"> <p>Your application has released the media player, which also releases any associated resources. You can no longer use this instance</p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p><span class="codeph">PTMediaPlayerStatusError</span> </p> </td> 
    <td colname="col2"> <p>An error occurred during the process. An error also might affect what your application can do next.</p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

The following table provides additional details:

>[!TIP]
>
>You can use the status to provide feedback on the process (for example, a spinner while waiting for the next status change) or to take the next step in playing the media, such as waiting for the appropriate status before calling the next method.
