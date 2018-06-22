---
---

[com.adobe.mediacore.timeline.advertising](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/package-detail.html)
[com.adobe.mediacore.timeline.advertising.policy](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/policy/package-detail.html)
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
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/Ad.html" format="html" scope="external">Ad</a></span></td> 
    <td colname="2">Class that defines the Ad abstraction and holds all ad information. It is defined by a unique ID, a duration, and a <span class="codeph">MediaResource</span>. The <span class="codeph">MediaResource</span> contains the URL where the actual ad content resides. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/AdAsset.html" format="html" scope="external">AdAsset</a></span> </td> 
    <td colname="2">Class that represents an asset to be displayed. Class representing an ad asset.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/AdBreak.html" format="html" scope="external">AdBreak</a></span></td> 
    <td colname="2">Class that gives a unified view on several ads that will be played at some point during playback.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/policy/AdBreakPolicy.html" format="html" scope="external">AdBreakPolicy</a></span> </td> 
    <td colname="2">Enumeration that defines the ad playback policy related to the user bypassing ads while seeking.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/AdBreakTimelineItem.html" format="html" scope="external">AdBreakTimelineItem</a></span> </td> 
    <td colname="2">Timeline item associated with the specific ad break.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/policy/AdBreakWatchedPolicy.html" format="html" scope="external">AdBreakWatchedPolicy</a></span> </td> 
    <td colname="2">Enumeration class for possible policies on when to mark an ad break as having been watched.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/AdClick.html" format="html" scope="external">AdClick</a></span> </td> 
    <td colname="2">Class that represents a click instance associated with an asset. This instance contains information about the click-through URL and the title that can be used to provide additional information to the user.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/policy/AdPolicy.html" format="html" scope="external">AdPolicy</a></span> </td> 
    <td colname="2">Enumeration class for possible policies on where to resume playing an ad break after seeking or trick-play mode.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/policy/AdPolicyMode.html" format="html" scope="external">AdPolicyMode</a></span> </td> 
    <td colname="2">Enumeration class that lists ways in which the player is playing, such as seeking or normal play.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/policy/AdPolicySelector.html" format="html" scope="external">AdPolicyInfo</a></span> </td> 
    <td colname="2">Interface that defines properties for <span class="codeph">AdPolicySelector</span> API calls. These properties provide the context for enforcing each ad behavior. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/policy/AdPolicySelector.html" format="html" scope="external">AdPolicySelector</a></span></td> 
    <td colname="2">An ad policy selector interface for enforcing ad behaviors. Applications can conform to this interface by implementing all the required methods or by extending the existing default policy selector class to customize specific behaviors.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/AdTimelineItem.html" format="html" scope="external">AdTimelineItem</a></span> </td> 
    <td colname="2">Timeline item associated with a specific ad.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/AuditudeAdResolver.html" scope="external" format="html">AuditudeAdResolver</a></span> </td> 
    <td colname="2">Class that handles primetime ad resolving in the 
     <ph conref="phrase_library_dhls_1.4.xml#c_psdk_phrase-library/auditude-name-long">
      Phrase
     </ph> process. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/AdType.html" format="html" scope="external">AdType</a></span> </td> 
    <td colname="2">Enumeration of all ad types supported by the 
     <ph conkeyref="phrases/primetime-sdk-name"></ph>. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/timeline/advertising/MetadataAdResolver.html" format="html" scope="external">MetadataAdResolver</a></span> </td> 
    <td colname="2">Class.</td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

