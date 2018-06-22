---
---

<table frame="all" colsep="1" rowsep="1" id="table_ios_notifications"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="50*" /> 
  <colspec colnum="2" colname="2" colwidth="50*" colsep="1" rowsep="1" /> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"> <b>Notification</b> </td> 
    <td colname="2"> <b>Meaning</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerAdBreakCompletedNotification </span> </td> 
    <td colname="2"> An ad break ended. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerAdBreakStartedNotification </span> </td> 
    <td colname="2"> An ad break started. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerAdClickNotification </span> </td> 
    <td colname="2"> A user clicked a banner ad. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerAdCompletedNotification </span> </td> 
    <td colname="2"> An individual ad ended. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerAdProgressNotification </span> </td> 
    <td colname="2"> An ad progressed; dispatched constantly while an ad plays. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerAdStartedNotification </span> </td> 
    <td colname="2"> An individual ad started. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTBackgroundManifestErrorNotification </span> </td> 
    <td colname="2"> Downloading the background manifest failed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerBufferingCompletedNotification </span> </td> 
    <td colname="2"> Buffering has completed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerBufferingStartedNotification </span> </td> 
    <td colname="2"> The media player enters a buffering state. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTAudioTrackChangeCompleted </span> </td> 
    <td colname="2"> A change on the audio track of the currently playing media has completed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTAudioTrackChangeStarted </span> </td> 
    <td colname="2"> A change on the audio track of the currently playing media is initiated. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerItemChangedNotification </span> </td> 
    <td colname="2"> A different <span class="codeph"> PTMediaPlayerItem </span> of the <span class="codeph"> PTMediaPlayer </span> has been set. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerItemDRMMetadataChanged </span> </td> 
    <td colname="2"> DRM metadata changed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerMediaSelectionOptionsAvailableNotification </span> </td> 
    <td colname="2"> There are new subtitles and alternate audio tracks ( <span class="codeph"> PTMediaSelectionOption </span>). </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerNewNotificationEntryAddedNotification </span> </td> 
    <td colname="2"> A new <span class="codeph"> PTNotification </span> has been added to the <span class="codeph"> PTNotificationHistoryItem </span> of the current <span class="codeph"> PTMediaPlayerItem </span>, that is, when a notification event is added to the notification history. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerPlayCompletedNotification </span> </td> 
    <td colname="2"> Media playback ended. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerSeekCompletedNotification </span> </td> 
    <td colname="2"> Seeking has completed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerSeekErrorNotification </span> </td> 
    <td colname="2"> The current seek operation has failed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerSeekStartedNotification </span> </td> 
    <td colname="2"> Seeking is starting. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerPlayStartedNotification </span> </td> 
    <td colname="2"> Playback started. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerStatusNotification </span> </td> 
    <td colname="2"> The player status changed. Possible status values are: 
     <ul id="ul_DDBE8CAD5D5A46D2AAA6B98F0754A881"> 
      <li id="li_48F9AD580BCB4BB8A5C2DFED0DF9970F"> <p> <span class="codeph"> PTMediaPlayerStatusCreated </span> </p> </li> 
      <li id="li_EDFB0765CF14422A95C9119DA3394163"> <p> <span class="codeph"> PTMediaPlayerStatusInitializing </span> </p> </li> 
      <li id="li_06E1576D50C646C19E88F0F14912F2C0"> <p> <span class="codeph"> PTMediaPlayerStatusInitialized </span> </p> </li> 
      <li id="li_E8B7157B5B234DFFABC2E5BEC241AB84"> <p> <span class="codeph"> PTMediaPlayerStatusReady </span> </p> </li> 
      <li id="li_FF2E66B390154EAA8791B4D874CC62E1"> <p> <span class="codeph"> PTMediaPlayerStatusPlaying </span> </p> </li> 
      <li id="li_6F3306832B7642E4BEE84068383AFAF3"> <p> <span class="codeph"> PTMediaPlayerStatusPaused </span> </p> </li> 
      <li id="li_AE579AB888954F89A7F1115CAC0655E6"> <p> <span class="codeph"> PTMediaPlayerStatusStopped </span> </p> </li> 
      <li id="li_A4CEB39374E84B4AA4F7202E67B9BE43"> <p> <span class="codeph"> PTMediaPlayerStatusCompleted </span> </p> </li> 
      <li id="li_C50EB9C459264641A9FF70EF901D7474"> <p> <span class="codeph"> PTMediaPlayerStatusError </span> </p> </li> 
     </ul> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerTimeChangeNotification </span> </td> 
    <td colname="2"> The playback current time changed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTMediaPlayerTimelineChangedNotification </span> </td> 
    <td colname="2"> The current player timeline changed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1" colsep="1" rowsep="1"> <span class="codeph"> PTTimedMetadataChangedNotification </span> </td> 
    <td colname="2"> The 
     <ph conkeyref="phrases/primetime-sdk-name">
       Phrase 
     </ph> encountered the first occurrence of a subscribed tag. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> PTTimedMetadataChangedInBackgroundNotification </span> </td> 
    <td colname="2"> <p>A subscribed tag is identified on the background manifest and a new <span class="codeph"> PTTimedMetadata </span> instance is prepared from it. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

