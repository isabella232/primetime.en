---
---

>`codeph MediaPlayer.AdPlaybackEventListener`
>>[!TIP]
>>
>>When ads are inserted into or removed from the media, dispatches the playback event [onTimelineUpdated](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.PlaybackEventListener.html#onTimelineUpdated()).
>
><table frame="all" colsep="1" rowsep="1"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="2" colwidth="1.31*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Event</th> 
    <th colname="2" class="entry">Meaning</th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdBreakComplete(com.adobe.mediacore.timeline.advertising.AdBreak)" format="html" scope="external">onAdBreakComplete</a> (AdBreak adBreak) </span></td> 
    <td colname="2">An ad break has played completely.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">onAdBreakSkipped</span></td> 
    <td colname="2">An ad break was skipped during playback.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdBreakStart(com.adobe.mediacore.timeline.advertising.AdBreak)" format="html" scope="external">onAdBreakStart</a> (AdBreak adBreak)</span></td> 
    <td colname="2">An ad break has started.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdClick(com.adobe.mediacore.timeline.advertising.AdBreak,%20com.adobe.mediacore.timeline.advertising.Ad,%20com.adobe.mediacore.timeline.advertising.AdClick)" format="html" scope="external">onAdClick</a> (AdBreak adBreak, Ad ad, AdClick adClick) </span></td> 
    <td colname="2">The user has clicked the ad. Provides information to your application about the ad that the user clicked, in response to your application calling <span class="codeph">notifyClick</span> on the <span class="codeph">MediaPlayerView</span>. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdComplete(com.adobe.mediacore.timeline.advertising.AdBreak)" format="html" scope="external">onAdComplete</a> (AdBreak adBreak, Ad ad) </span></td> 
    <td colname="2">An ad has played completely.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdProgress(com.adobe.mediacore.timeline.advertising.AdBreak,com.adobe.mediacore.timeline.advertising.Ad,%20int)" format="html" scope="external">onAdProgress</a> (AdBreak adBreak, Ad ad, int percentage)</span> </td> 
    <td colname="2">Ad playback has progressed. Dispatched multiple times while an ad plays.</td> 
   </tr> 
   <tr rowsep="0"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.AdPlaybackEventListener.html#onAdStart(com.adobe.mediacore.timeline.advertising.AdBreak,%20com.adobe.mediacore.timeline.advertising.Ad)" format="html" scope="local">onAdStart</a> (AdBreak adBreak, Ad ad)</span></td> 
    <td colname="2">An ad has started.</td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
