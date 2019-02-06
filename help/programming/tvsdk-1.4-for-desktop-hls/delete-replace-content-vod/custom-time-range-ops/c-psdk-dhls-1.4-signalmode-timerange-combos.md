---
description: null
seo-description: null
seo-title: Signaling mode and time range
title: Signaling mode and time range
uuid: a4d2b0f3-49ce-4a07-a460-9e63bb91b5d3
---

# Signaling mode and time range{#signaling-mode-and-time-range}

<table> 
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
      (range.begin,&nbsp; 
     
&nbsp;range.end) 
    </codeblock> </td> 
   <td> 
    <codeblock>
      (range.begin,&nbsp; 
     
&nbsp;range.end) 
    </codeblock> </td> 
   <td> 
    <codeblock>
      (range.begin,&nbsp; 
     
&nbsp;range.end,&nbsp; 
     
&nbsp;replaceDuration) 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ServerMap </span> Signaling Mode </td> 
   <td> 
    <codeblock>
      placement&nbsp;=&nbsp; 
     
&nbsp;&nbsp;new&nbsp;Placement(&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.CUSTOM_RANGE,&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.begin,&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.end&nbsp;-&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementMode.MARK&nbsp;); 
    </codeblock> </td> 
   <td> 
    <codeblock>
      placement&nbsp;=&nbsp; 
     
&nbsp;&nbsp;new&nbsp;Placement(&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.CUSTOM_RANGE,&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.begin,&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.end&nbsp;-&nbsp;range.begin,&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementMode.DELETE&nbsp;); 
    </codeblock> </td> 
   <td> N/A (automatic CustomRange signaling mode) </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ManifestCue </span> Signaling Mode </td> 
   <td> 
    <codeblock>
      placement&nbsp;=&nbsp; 
     
new&nbsp;Placement( 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.CUSTOM_RANGE, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.end&nbsp;-&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementMode.MARK 
     
); 
    </codeblock> </td> 
   <td> 
    <codeblock>
      placement&nbsp;=&nbsp; 
     
&nbsp;&nbsp;new&nbsp;Placement( 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.CUSTOM_RANGE, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.end&nbsp;-&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementMode.DELETE 
     
); 
    </codeblock> </td> 
   <td> N/A (automatic CustomRange signaling mode) </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> CustomRange </span> Signaling Mode </td> 
   <td> 
    <codeblock>
      placement&nbsp;=&nbsp; 
     
&nbsp;&nbsp;new&nbsp;Placement( 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.CUSTOM_RANGE, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.end&nbsp;-&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementMode.MARK 
     
); 
    </codeblock> </td> 
   <td> 
    <codeblock>
      placement&nbsp;=&nbsp; 
     
&nbsp;&nbsp;new&nbsp;Placement( 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.CUSTOM_RANGE, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.end&nbsp;-&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementMode.DELETE 
     
); 
    </codeblock> </td> 
   <td> 
    <codeblock>
      placement1&nbsp;=&nbsp; 
     
&nbsp;&nbsp;new&nbsp;Placement( 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.CUSTOM_RANGE, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;range.end&nbsp;-&nbsp;range.begin, 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementMode.MARK 
     
); 
     
placement2&nbsp;=&nbsp;placement&nbsp;=&nbsp; 
     
&nbsp;&nbsp;new&nbsp;Placement(/ 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.MID_ROLL( 
     
&nbsp;&nbsp;&nbsp;&nbsp;PlacementType.PRE_ROLL), 
     
&nbsp;&nbsp;&nbsp;&nbsp;rangeDuration, 
     
&nbsp;&nbsp;&nbsp;&nbsp;placementMode 
     
); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
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
      (range.begin,&nbsp; 
     
&nbsp;range.end) 
    </codeblock> </td> 
   <td> 
    <codeblock>
      (range.begin,&nbsp; 
     
&nbsp;range.end) 
    </codeblock> </td> 
   <td> 
    <codeblock>
      (range.begin,&nbsp; 
     
&nbsp;range.end,&nbsp; 
     
&nbsp;replaceDuration) 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> SeverMap </span> Signaling Mode </td> 
   <td> Not present (ad is disabled). </td> 
   <td> 
    <codeblock>
      placement&nbsp;=&nbsp; 
     
&nbsp;new&nbsp;Placement( 
     
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
      placement&nbsp;=&nbsp; 
     
&nbsp;new&nbsp;Placement( 
     
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
</table>

