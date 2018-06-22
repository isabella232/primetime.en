---
---

[com.adobe.mediacore.events](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/package-detail.html)
<table frame="all" colsep="1" rowsep="1" id="table_B542FF31CAAA405F9BBD5AFD89810BCD"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="38*" /> 
  <colspec colnum="2" colname="2" colwidth="62*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Name </th> 
    <th colname="2" class="entry">Meaning </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html" format="html" scope="external">AdBreakPlaybackEvent</a></span> </td> 
    <td colname="2">Class. An ad break started or completed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdClickEvent.html" scope="external" format="html">AdClickEvent</a></span> </td> 
    <td colname="2">Class. The user clicked an ad. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html" format="html" scope="external">AdPlaybackEvent</a></span></td> 
    <td colname="2">Class. The player played an ad. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/BufferEvent.html" format="html" scope="external">BufferEvent</a></span> </td> 
    <td colname="2">Class. The player started or stopped buffering. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/CustomAdEvent.html" format="html" scope="external">CustomAdEvent</a></span> </td> 
    <td colname="2">Class. The player displays custom ad loading status and can ignore ads that have errors or are taking too long to load. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/DRMMetadataInfoEvent.html" format="html" scope="external">DRMMetadataInfoEvent</a></span> </td> 
    <td colname="2">Class. New DRM metadata is associated with the current item. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/LoadInformationEvent.html" format="html" scope="external">LoadInformationEvent</a></span> </td> 
    <td colname="2"> Class. Download information is available for the current media stream being played. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerItemEvent.html" format="html" scope="external">MediaPlayerItemEvent</a></span> </td> 
    <td colname="2">Class. A media player item has been created. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerItemLoaderEvent.html" format="html" scope="external">MediaPlayerItemLoaderEvent</a></span> </td> 
    <td colname="2">Class. A load operation has completed. Dispatched by <span class="codeph">MediaPlayerItemLoader</span> to notify its clients. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerStatusChangeEvent.html" format="html" scope="external">MediaPlayerStatusChangeEvent</a></span> </td> 
    <td colname="2">Class. The media player status changed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/MediaPlayerViewEvent.html" format="html" scope="external">MediaPlayerViewEvent</a></span> </td> 
    <td colname="2"> Class. The <span class="codeph">MediaPlayerView</span> was clicked. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/PlaybackRateEvent.html" format="html" scope="external">PlaybackRateEvent</a></span> </td> 
    <td colname="2"> Class. The media player's playback rate changes. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/ProfileEvent.html" format="html" scope="external">ProfileEvent</a></span> </td> 
    <td colname="2">Class. The media player’s adaptive bit rate switching algorithm has switched to another profile due to network or machine conditions. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/SeekEvent.html" format="html" scope="external">SeekEvent</a></span> </td> 
    <td colname="2">Class. The player started seeking or the seek operation completed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/SizeAvailableEvent.html" format="html" scope="external">SizeAvailableEvent</a></span> </td> 
    <td colname="2">Class. The video size is available. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimeChangeEvent.html" format="html" scope="external">TimeChangeEvent</a></span> </td> 
    <td colname="2">Class. The media player’s status changed. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimedMetadataEvent.html" format="html" scope="external">TimedMetadataEvent</a></span> </td> 
    <td colname="2">Class. A timed metadata is processed by the opportunity detector. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimelineEvent.html" format="html" scope="external">TimelineEvent</a></span> </td> 
    <td colname="2">Class. The media player timeline has changed. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

