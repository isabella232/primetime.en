---
---


<table> 
 <tgroup cols="4"> 
  <thead> 
   <tr> 
    <th class="entry"> </th> 
    <th class="entry"> MARK </th> 
    <th class="entry"> DELETE </th> 
    <th class="entry"> REPLACE </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td> <span class="codeph"> CustomRange OpportunityGenerator </span> </td> 
    <td> 
     <codeblock>
       (range.begin, 
      <discoiqbr /> range.end) 
     </codeblock> </td> 
    <td> 
     <codeblock>
       (range.begin, 
      <discoiqbr /> range.end) 
     </codeblock> </td> 
    <td> 
     <codeblock>
       (range.begin, 
      <discoiqbr /> range.end, 
      <discoiqbr /> replaceDuration) 
     </codeblock> </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> ServerMap </span> Signaling Mode </td> 
    <td> 
     <codeblock>
       placement = 
      <discoiqbr /> new Placement( 
      <discoiqbr /> PlacementType.CUSTOM_RANGE, 
      <discoiqbr /> range.begin, 
      <discoiqbr /> range.end - 
      <discoiqbr /> range.begin, 
      <discoiqbr /> PlacementMode.MARK ); 
     </codeblock> </td> 
    <td> 
     <codeblock>
       placement = 
      <discoiqbr /> new Placement( 
      <discoiqbr /> PlacementType.CUSTOM_RANGE, 
      <discoiqbr /> range.begin, 
      <discoiqbr /> range.end - range.begin, 
      <discoiqbr /> PlacementMode.DELETE ); 
     </codeblock> </td> 
    <td> N/A (automatic CustomRange signaling mode) </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> ManifestCue </span> Signaling Mode </td> 
    <td> 
     <codeblock>
       placement = 
      <discoiqbr />new Placement( 
      <discoiqbr /> PlacementType.CUSTOM_RANGE, 
      <discoiqbr /> range.begin, 
      <discoiqbr /> range.end - range.begin, 
      <discoiqbr /> PlacementMode.MARK 
      <discoiqbr />); 
     </codeblock> </td> 
    <td> 
     <codeblock>
       placement = 
      <discoiqbr /> new Placement( 
      <discoiqbr /> PlacementType.CUSTOM_RANGE, 
      <discoiqbr /> range.begin, 
      <discoiqbr /> range.end - range.begin, 
      <discoiqbr /> PlacementMode.DELETE 
      <discoiqbr />); 
     </codeblock> </td> 
    <td> N/A (automatic CustomRange signaling mode) </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> CustomRange </span> Signaling Mode </td> 
    <td> 
     <codeblock>
       placement = 
      <discoiqbr /> new Placement( 
      <discoiqbr /> PlacementType.CUSTOM_RANGE, 
      <discoiqbr /> range.begin, 
      <discoiqbr /> range.end - range.begin, 
      <discoiqbr /> PlacementMode.MARK 
      <discoiqbr />); 
     </codeblock> </td> 
    <td> 
     <codeblock>
       placement = 
      <discoiqbr /> new Placement( 
      <discoiqbr /> PlacementType.CUSTOM_RANGE, 
      <discoiqbr /> range.begin, 
      <discoiqbr /> range.end - range.begin, 
      <discoiqbr /> PlacementMode.DELETE 
      <discoiqbr />); 
     </codeblock> </td> 
    <td> 
     <codeblock>
       placement1 = 
      <discoiqbr /> new Placement( 
      <discoiqbr /> PlacementType.CUSTOM_RANGE, 
      <discoiqbr /> range.begin, 
      <discoiqbr /> range.end - range.begin, 
      <discoiqbr /> PlacementMode.MARK 
      <discoiqbr />); 
      <discoiqbr />placement2 = placement = 
      <discoiqbr /> new Placement(/ 
      <discoiqbr /> PlacementType.MID_ROLL( 
      <discoiqbr /> PlacementType.PRE_ROLL), 
      <discoiqbr /> rangeDuration, 
      <discoiqbr /> placementMode 
      <discoiqbr />); 
     </codeblock> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>


<table> 
 <tgroup cols="4"> 
  <thead> 
   <tr> 
    <th class="entry"> </th> 
    <th class="entry"> MARK </th> 
    <th class="entry"> DELETE </th> 
    <th class="entry"> REPLACE </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td> <span class="codeph"> AdSignalingMode OpportunityGenerator </span> </td> 
    <td> 
     <codeblock>
       (range.begin, 
      <discoiqbr /> range.end) 
     </codeblock> </td> 
    <td> 
     <codeblock>
       (range.begin, 
      <discoiqbr /> range.end) 
     </codeblock> </td> 
    <td> 
     <codeblock>
       (range.begin, 
      <discoiqbr /> range.end, 
      <discoiqbr /> replaceDuration) 
     </codeblock> </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> SeverMap </span> Signaling Mode </td> 
    <td> Not present (ad is disabled). </td> 
    <td> 
     <codeblock>
       placement = 
      <discoiqbr /> new Placement( 
      <discoiqbr />PlacementType.SERVER_MAP, 
      <discoiqbr />Placement.UNKNOWN_TIME, 
      <discoiqbr />Placement.UNKNOWN_DURATION, 
      <discoiqbr />PlacementMode.DEFAULT); 
     </codeblock> </td> 
    <td> N/A (automatic <span class="codeph"> CustomRange </span> signaling mode) </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> ManifestCue </span> Signaling Mode </td> 
    <td> Not present (ad is disabled). </td> 
    <td> 
     <codeblock>
       placement = 
      <discoiqbr /> new Placement( 
      <discoiqbr />PlacementType.PRE_ROLL, 
      <discoiqbr />playhead, 
      <discoiqbr />Placement.UNKNOWN_DURATION, 
      <discoiqbr />PlacementMode.DEFAULT); 
     </codeblock> </td> 
    <td> N/A (automatic <span class="codeph"> CustomRange </span> signaling mode) </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> CustomRange </span> Signaling Mode </td> 
    <td> Not present (ad is disabled). </td> 
    <td> None </td> 
    <td> None (taken care of in <span class="codeph"> CustomRangeOpportunityGenerator </span>) </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

