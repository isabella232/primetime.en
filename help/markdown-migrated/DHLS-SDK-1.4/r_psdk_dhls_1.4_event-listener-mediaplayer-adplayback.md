---
---

>`codeph MediaPlayer`
>>[!TIP]
>>
>>When ads are inserted into or removed from the media, dispatches the playback event `codeph TimelineEvent.[TIMELINE_UPDATED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/TimelineEvent.html#TIMELINE_UPDATED)`.
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
    <td colname="1"><span class="codeph">AdBreakPlaybackEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_COMPLETED" format="html" scope="external">AD_BREAK_COMPLETED</a> </span></td> 
    <td colname="2">An ad break has played completely.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">AdBreakPlaybackEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_SKIPPED" format="http" scope="external">AD_BREAK_SKIPPED</a></span></td> 
    <td colname="2">An ad break was skipped during playback.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">AdBreakPlaybackEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdBreakPlaybackEvent.html#AD_BREAK_STARTED" format="html" scope="external">AD_BREAK_STARTED</a> </span></td> 
    <td colname="2">An ad break has started.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">AdClickEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdClickEvent.html#AD_CLICK" format="html" scope="external">AD _CLICK</a></span></td> 
    <td colname="2">The user has clicked the ad. Provides information to your application about the ad that the user clicked, in response to your application calling <span class="codeph">notifyClick</span> on the <span class="codeph">MediaPlayerView</span>. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">AdPlaybackEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_COMPLETED" format="html" scope="external">AD _COMPLETED</a></span> </td> 
    <td colname="2">An ad has played completely.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">AdPlaybackEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_PROGRESS" format="html" scope="external">AD _PROGRESS</a></span> </td> 
    <td colname="2">Ad playback has progressed. Dispatched multiple times while an ad plays.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">AdPlaybackEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_STARTED" format="html" scope="external">AD _SEEK</a></span> </td> 
    <td colname="2">A seek has occurred across ad boundaries or within an ad.</td> 
   </tr> 
   <tr rowsep="0"> 
    <td colname="1"><span class="codeph">AdPlaybackEvent.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/AdPlaybackEvent.html#AD_STARTED" format="html" scope="external">AD _STARTED</a></span></td> 
    <td colname="2">An ad has started.</td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
