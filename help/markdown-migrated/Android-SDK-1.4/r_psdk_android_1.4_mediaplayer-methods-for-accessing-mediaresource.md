---
---

<table frame="all" colsep="1" rowsep="1" id="table_77B55D506FE24326A03D97AA087231FF"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="2" colwidth="41*" /> 
  <colspec colnum="2" colname="3" colwidth="46*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="2" class="entry"> Method </th> 
    <th colname="3" class="entry"> Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td namest="2" nameend="3"> <b>Ad tags</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> List&lt;String&gt; getAdTags() </span> </td> 
    <td colname="3"> <p>Provides the list of ad tags that are used for the ad placement process. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="2" nameend="3"> <b>Live stream </b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> boolean isLive(); </span> </td> 
    <td colname="3"> <p>True if the stream is live; false if it is VOD. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="2" nameend="3"> <b>DRM protected</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> boolean isProtected(); </span> </td> 
    <td colname="3"> <p>True if the stream is DRM protected. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> List&lt;DRMMetadataInfo&gt; getDRMMetadataInfos(); </span> </td> 
    <td colname="3"> <p>Lists all the DRM metadata objects discovered in the manifest. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="2" nameend="3"> <b>Closed captions</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> boolean hasClosedCaptions(); </span> </td> 
    <td colname="3"> <p>True if closed-caption tracks are available. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> List&lt;ClosedCaptionsTrack&gt; getClosedCationsTracks(); </span> </td> 
    <td colname="3"> <p>Provides a list of available closed-caption tracks. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> ClosedCaptionsTrack get SelectedClosedCaptionsTrack(); </span> </td> 
    <td colname="3"> <p>Retrieves the current closed caption track selected with <span class="codeph"> SelectClosedCaptionsTrack </span>. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> selectClosedCaptionsTrack ( ClosedCaptionsTrack closedCaptionsTrack) </span> </td> 
    <td colname="3"> <p>Sets a closed-caption track to be the current closed-caption track. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="2" nameend="3"> <b>Alternate audio tracks </b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> boolean hasAlternateAudio(); </span> </td> 
    <td colname="3"> <p>True if the stream has alternate audio tracks. </p> <p type="tip">Note:  The main (default) audio track is also part of the alternate audio track list. </p> <p> 
      <ph conkeyref="phrases/primetime-sdk-name" /> for Android considers the main audio track to be one of the items in the alternate audio track list. Because of this, the only case where <span class="codeph"> MediaPlayerItem.hasAlternateAudio </span> returns false is when the stream has no audio at all. If the content has only one audio track, this method returns true, and <span class="codeph"> MediaPlayerItem.getAudioTracks </span> returns a list with a single element (the default audio track). </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> List&lt;AudioTrack&gt; getAudioTracks(); </span> </td> 
    <td colname="3"> Provides a list of available alternate audio tracks. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> List&lt;AudioTrack&gt; getAudioTracks(); </span> </td> 
    <td colname="3"> <p>Provides a list of available alternate audio tracks. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> AudioTrack getSelectedAudioTrack(); </span> </td> 
    <td colname="3"> <p>Retrieves the audio track selected with <span class="codeph"> selectAudioTrack </span>. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> selectAudioTrack ( AudioTrack audioTrack ) </span> </td> 
    <td colname="3"> <p>Selects an audio track to be the current audio track. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="2" nameend="3"> <b>Timed metadata</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> boolean hasTimedMetadata(); </span> </td> 
    <td colname="3"> <p>True if the stream has associated timed metadata. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> List&lt;TimedMetadata&gt; getTimedMetadata(); </span> </td> 
    <td colname="3"> <p>Provides a list of the timed metadata objects associated with the stream. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> boolean isDynamic(); </span> </td> 
    <td colname="3"> <p>True if the stream is a multiple bit rate (MBR) stream. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> List&lt;Profile&gt; getProfiles(); </span> </td> 
    <td colname="3"> <p>Provides a list of the associated bit rate profiles. For each profile, you can retrieve its bit rate and the height and width of the profile. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="2" nameend="3"> <b>Trick play </b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> boolean isTrickPlaySupported(); </span> </td> 
    <td colname="3"> <p>True if the player supports fast forward, rewind, and resume. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> List&lt; Float&gt; getAvailablePlaybackRates </span> </td> 
    <td colname="3"> <p>Provides the list of available playback rates in the context of the trick-play feature. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="2" nameend="3"> <b>Media resource</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="2"> <span class="codeph"> MediaResource getResource(); </span> </td> 
    <td colname="3"> <p>Returns the media resource associated with this item. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>


