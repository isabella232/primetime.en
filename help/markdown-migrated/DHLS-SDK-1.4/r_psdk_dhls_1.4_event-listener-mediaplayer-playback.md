---
---

>To be notified about all playback-related events, register listeners with the `codeph MediaPlayer` object for the following events.
>
>
><table frame="all" colsep="1" rowsep="1"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="1*" /> 
  <colspec colnum="2" colname="2" colwidth="2*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Event</th> 
    <th colname="2" class="entry">Meaning</th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>Playback</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1">PlaybackRateEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/PlaybackRateEvent.html#RATE_SELECTED" format="html" scope="external">RATE_SELECTED</a> </td> 
    <td colname="2">The user or 
     <ph conkeyref="phrases/primetime-sdk-name" /> has selected a new playback rate, such as fast forward, rewind, or resume playing at a normal speed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1">PlaybackRateEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/PlaybackRateEvent.html#RATE_PLAYING" format="html" scope="external">RATE_PLAYING</a> </td> 
    <td colname="2">A new playback rate is visible on the screen.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> TimeChangeEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimeChangeEvent.html#TIME_CHANGED" format="html" scope="external">TIME_CHANGED</a> </td> 
    <td colname="2">The current playhead position of the media has changed. Dispatched periodically when the current time has changed, every 250 ms or more.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>Media Player</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1">MediaPlayerStatus ChangeEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerStatusChangeEvent.html#STATUS_CHANGED" format="html" scope="external">STATUS_CHANGED</a> </td> 
    <td colname="2">The status of the media player has changed. Your application should handle errors in this event’s callback.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1">ProfileEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/ProfileEvent.html#PROFILE_CHANGED" format="html" scope="external">PROFILE_CHANGED</a> </td> 
    <td colname="2">The media player’s current profile has changed. Use the <span class="codeph">ProfileEvent.profile</span> property to get the new profile that is being played. Use the <span class="codeph">time</span> property to get the time when this event occurred. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>MediaplayerItem</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1">MediaPlayerItem Event.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerItemEvent.html#ITEM_CREATED" format="html" scope="external">ITEM_CREATED</a> </td> 
    <td colname="2">A <span class="codeph">MediaPlayerItem</span> has been created. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1">MediaPlayerItem Event.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerItemEvent.html#ITEM_UPDATED" format="html" scope="external">ITEM_UPDATED</a> </td> 
    <td colname="2">The media player has successfully updated the media in either of these cases: 
     <ul> 
      <li>When a manifest refresh occurs for a live asset.</li> 
      <li>When a VOD or live asset has closed captioning and activity is first discovered for a closed captioning track.</li> 
     </ul> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>Captions and Audio</b> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> MediaPlayerItem Event.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerItemEvent.html#CAPTION_UPDATED" format="html" scope="external">CAPTION_UPDATED</a> </td> 
    <td colname="2">A new closed captioning track has been detected in the media stream and the <span class="codeph">closedCaptionsTracks</span> collection has been updated. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td namest="1" nameend="2"><b>Manifest and Timeline</b> </td> 
   </tr> 
   <tr rowsep="0"> 
    <td colname="1">TimelineEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimelineEvent.html#TIMELINE_UPDATED" format="html" scope="external">TIMELINE_UPDATED</a> </td> 
    <td colname="2">The media player has added or removed ads, so it has an updated timeline. <p>The manifest refreshed for a live asset and old ad breaks were removed from the timeline or new ad opportunities (cue points) were discovered. The media player tries to resolve and place any new ads on the timeline.</p><p> Use this event to check whether the timeline has any updates (VOD does not change during playback). You can then retrieve the timeline using <a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/MediaPlayer.html#timeline" format="html" scope="external">MediaPlayer.timeline</a>. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
