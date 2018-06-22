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
       range.end) 
     </codeblock> </td> 
    <td> 
     <codeblock>
       (range.begin, 
       range.end) 
     </codeblock> </td> 
    <td> 
     <codeblock>
       (range.begin, 
       range.end, 
       replaceDuration) 
     </codeblock> </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> ServerMap </span> Signaling Mode </td> 
    <td> 
     <codeblock>
       placement = 
       new Placement( 
       PlacementType.CUSTOM_RANGE, 
       range.begin, 
       range.end - 
       range.begin, 
       PlacementMode.MARK ); 
     </codeblock> </td> 
    <td> 
     <codeblock>
       placement = 
       new Placement( 
       PlacementType.CUSTOM_RANGE, 
       range.begin, 
       range.end - range.begin, 
       PlacementMode.DELETE ); 
     </codeblock> </td> 
    <td> N/A (automatic CustomRange signaling mode) </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> ManifestCue </span> Signaling Mode </td> 
    <td> 
     <codeblock>
       placement = 
      new Placement( 
       PlacementType.CUSTOM_RANGE, 
       range.begin, 
       range.end - range.begin, 
       PlacementMode.MARK 
      ); 
     </codeblock> </td> 
    <td> 
     <codeblock>
       placement = 
       new Placement( 
       PlacementType.CUSTOM_RANGE, 
       range.begin, 
       range.end - range.begin, 
       PlacementMode.DELETE 
      ); 
     </codeblock> </td> 
    <td> N/A (automatic CustomRange signaling mode) </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> CustomRange </span> Signaling Mode </td> 
    <td> 
     <codeblock>
       placement = 
       new Placement( 
       PlacementType.CUSTOM_RANGE, 
       range.begin, 
       range.end - range.begin, 
       PlacementMode.MARK 
      ); 
     </codeblock> </td> 
    <td> 
     <codeblock>
       placement = 
       new Placement( 
       PlacementType.CUSTOM_RANGE, 
       range.begin, 
       range.end - range.begin, 
       PlacementMode.DELETE 
      ); 
     </codeblock> </td> 
    <td> 
     <codeblock>
       placement1 = 
       new Placement( 
       PlacementType.CUSTOM_RANGE, 
       range.begin, 
       range.end - range.begin, 
       PlacementMode.MARK 
      ); 
      placement2 = placement = 
       new Placement(/ 
       PlacementType.MID_ROLL( 
       PlacementType.PRE_ROLL), 
       rangeDuration, 
       placementMode 
      ); 
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
       range.end) 
     </codeblock> </td> 
    <td> 
     <codeblock>
       (range.begin, 
       range.end) 
     </codeblock> </td> 
    <td> 
     <codeblock>
       (range.begin, 
       range.end, 
       replaceDuration) 
     </codeblock> </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> SeverMap </span> Signaling Mode </td> 
    <td> Not present (ad is disabled). </td> 
    <td> 
     <codeblock>
       placement = 
       new Placement( 
      PlacementType.SERVER_MAP, 
      Placement.UNKNOWN_TIME, 
      Placement.UNKNOWN_DURATION, 
      PlacementMode.DEFAULT); 
     </codeblock> </td> 
    <td> N/A (automatic <span class="codeph"> CustomRange </span> signaling mode) </td> 
   </tr> 
   <tr> 
    <td> <span class="codeph"> ManifestCue </span> Signaling Mode </td> 
    <td> Not present (ad is disabled). </td> 
    <td> 
     <codeblock>
       placement = 
       new Placement( 
      PlacementType.PRE_ROLL, 
      playhead, 
      Placement.UNKNOWN_DURATION, 
      PlacementMode.DEFAULT); 
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

