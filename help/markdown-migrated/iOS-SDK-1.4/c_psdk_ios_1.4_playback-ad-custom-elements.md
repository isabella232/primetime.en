---
description: provides classes and methods you can use to customize the playback behavior of content that contains advertising.
seo-description: provides classes and methods you can use to customize the playback behavior of content that contains advertising.
seo-title: API elements for ad playback
title: API elements for ad playback
---

# API elements for ad playback

<table id="table_B07E373B9D2B425AB36466B1D42411AD"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1*" /> 
  <colspec colnum="2" colname="col2" colwidth="2*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry">API element</th> 
    <th colname="col2" class="entry">Content that supports advertising</th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"><span class="codeph">PTAdMetadata</span> </td> 
    <td colname="col2">Control whether an ad break should be marked as having been watched by a viewer, and if yes, when to mark it. Set and get the watched policy using <span class="codeph">adBreakAsWatched</span> property. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">PTAdPolicySelector</span></td> 
    <td colname="col2"> Protocol that allows customization of 
     <ph conkeyref="phrases/primetime-sdk-name" /> ad behavior. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">PTDefaultAdPolicySelector</span> </td> 
    <td colname="col2">Class that implements the default 
     <ph conkeyref="phrases/primetime-sdk-name" /> behavior. Your application can override this class to customize the default behaviors without implementing the complete interface. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">PTMediaPlayer</span> </td> 
    <td colname="col2"> 
     <ul id="ul_37700A741403448A8760FDDA68B099AA"> 
      <li id="li_B465170D449E49489C5924572BEEB4A5"><span class="codeph">localTime</span>. <p>This is the local time of the playback, excluding the placed ad breaks.</p> </li> 
      <li id="li_D9D68CF428904BB2B84E1BCE828A90DC"><span class="codeph">seekToLocalTime</span> . <p>Here, the seek occurs relative to a local time in the stream.</p> </li> 
      <li id="li_9DBCA75537DC4824AA66B53A3FA28812"><span class="codeph">getTimeline.convertToLocalTime</span>. <p>The virtual position on the timeline is converted to the local position.</p> </li> 
     </ul> </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">PTAdBreak</span> </td> 
    <td colname="col2"><span class="codeph">isWatched</span> property. Indicates whether the viewer has watched the ad. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

The following API elements are useful for customizing playback: <!-- Q: Are there iOS equivs for the AdBreakPolicy and AdPolicy that are in other platforms? -->

