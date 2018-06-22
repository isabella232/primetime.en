---
---

[com.adobe.mediacore.timeline.advertising](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/package-summary.html)
[com.adobe.mediacore.timeline.advertising.auditude](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/auditude/package-summary.html)
<table frame="all" colsep="1" rowsep="1" id="table_1A59E777BA99466793D586286F19E933"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="30*" /> 
  <colspec colnum="2" colname="2" colwidth="70*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Name</th> 
    <th colname="2" class="entry">Description</th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/Ad.html" format="html" scope="external">Ad</a> </span></td> 
    <td colname="2">Class that defines the Ad abstraction and holds all ad information. It is defined by a unique ID, a duration, and a <span class="codeph">MediaResource</span>. The <span class="codeph">MediaResource</span> contains the URL where the actual ad content resides. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/AdAsset.html" format="html" scope="external">AdAsset</a></span> </td> 
    <td colname="2">Class that represents an asset to be displayed. Class representing an ad asset.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/AdBreak.html" format="html" scope="external">AdBreak</a> </span></td> 
    <td colname="2">Class that gives a unified view on several ads that will be played at some point during playback.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/AdBreakPlacement.html" format="html" scope="external">AdBreakPlacement</a> </span></td> 
    <td colname="2">Ad break placement operation class.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/AdBreakPolicy.html" format="html" scope="external">AdBreakPolicy</a> </span> </td> 
    <td colname="2">Enumeration that defines the ad playback policy related to the user bypassing ads while seeking.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/AdClick.html" format="html" scope="external">AdClick</a> </span> </td> 
    <td colname="2">Class that represents a click instance associated with an asset. This instance contains information about the click-through URL and the title that can be used to provide additional information to the user.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/AdPolicyInfo.html" format="html" scope="external">AdPolicyInfo</a> </span> </td> 
    <td colname="2">Interface that defines properties for AdPolicySelector API calls. These properties provide the context for enforcing each ad behavior.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/AdPolicySelector.html" format="html" scope="external">AdPolicySelector</a> </span> </td> 
    <td colname="2">An ad policy selector interface for enforcing ad behaviors. Applications can conform to this interface by implementing all the required methods or by extending the existing default policy selector class to customize specific behaviors.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">auditude.AuditudeAdProvider</span></td> 
    <td colname="2">Deprecated. Use AuditudeResolver.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">
      <ph>
       auditude.
      </ph><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/auditude/AuditudeResolver.html" format="html" scope="external">AuditudeResolver</a> </span></td> 
    <td colname="2"> Class that handles primetime ad resolving in the 
     <ph conref="phrase_library_android_1.4.xml#c_psdk_phrase-library/auditude-name-long">
      Phrase
     </ph> process. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1">
     <ph>
      auditude.
     </ph><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/auditude/AuditudeTracker.html" format="html" scope="external">AuditudeTracker</a> </td> 
    <td colname="2">Class that implements the ContentTracker interface and defines Primetime ad-tracking events.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/ContentResolver.html" format="html" scope="external">ContentResolver</a> </span> </td> 
    <td colname="2">Class that handles the ad-resolving part in the 
     <ph conref="phrase_library_android_1.4.xml#c_psdk_phrase-library/auditude-name-long">
      Phrase
     </ph> process. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/ContentTracker.html" format="html" scope="external">ContentTracker</a> </span></td> 
    <td colname="2">Interface that defines the protocol that you must implement if you want to create an ad-tracking module that is designed to integrate with the 
     <ph conkeyref="phrases/primetime-sdk-name" /> library or a custom ad tracker. <p>This interface requires that you define the way ad-progress events are reported to the remote ad-tracking system.</p> </td> 
   </tr> 
   <tr rowsep="0"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/timeline/advertising/PlacementInformation.html" format="html" scope="external">PlacementInformation</a> </span></td> 
    <td colname="2">Class that abstracts a placement information request. Each resolved ad must have one placement information attached to it. The placement information describes where the ad is intended to be placed on the timeline. It contains information such as: 
     <ul id="ul_A9105A78F0C24488BCD5E3F2EE62A3EE"> 
      <li id="li_01E968A4330D4B40BA1EB6F4A6000FFD">Placement position (in ms)</li> 
      <li id="li_A3DC9498BEE14FBA9E7A5D26874F3984">Type of the placement (pre-roll, mid-roll, or post-roll)</li> 
      <li id="li_4B9094DD318B4792854A377CC6064232">Duration of the main content chunk that is about to be replaced</li> 
     </ul> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

