---
seo-title: Play Rights
title: Play Rights
uuid: 90f2a7a6-6637-4d10-9afe-6d2e77fc4185
---

# Play Rights {#play-rights}

The following table describes the Play Rights preferences: 

<table frame="all" colsep="1" rowsep="1" class="+ topic/table adobe-d/table " id="table_p1j_d2z_n4"> 
 <thead class="- topic/thead "> 
  <tr rowsep="1" class="- topic/row "> 
   <th class="- topic/entry entry" colspan="2"> Preference </th> 
   <th colname="3" class="- topic/entry entry"> Description </th> 
  </tr> 
 </thead>
 <tbody class="- topic/tbody "> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> Playback Window </td> 
   <td colname="3" class="- topic/entry "> The duration a license is valid (in minutes) after the first time the user plays the protected content. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> Output Protection </td> 
   <td colname="3" class="- topic/entry "> Controls whether output to external rendering devices should be protected. Analog and digital outputs can be specified independently. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> Restrictions </td> 
   <td colname="3" class="- topic/entry "> Blacklist of client versions not permitted to play content. All columns are optional. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> DRM </td> 
   <td colname="3" class="- topic/entry "> Specifies a list of DRM versions that are not permitted to play protected content. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> Runtime </td> 
   <td colname="3" class="- topic/entry "> Specifies a list of Runtime versions that are not permitted to play protected content. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> Minimum Security Level </td> 
   <td colname="3" class="- topic/entry "></td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> DRM </td> 
   <td colname="3" class="- topic/entry "> Minimum DRM security level required to play protected content. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> Runtime </td> 
   <td colname="3" class="- topic/entry "> Minimum Runtime security level required to play protected content. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> <p class="- topic/p ">Allowed Applications </p> </td> 
   <td colname="3" class="- topic/entry "> Whitelist of client applications permitted to play content. If not applications are specified, any SWF or AIR application is allowed. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> SWF </td> 
   <td colname="3" class="- topic/entry "> List of SWF URLs permitted to play protected content. </td> 
  </tr> 
  <tr rowsep="0" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> AIR </td> 
   <td colname="3" class="- topic/entry "> List of AIR applications permitted to play protected content. Publisher ID is required, the remaining fields are optional. </td> 
  </tr> 
 </tbody> 
</table>

Flash Access Manager supports policies containing multiple Play Rights. To create a policy with more than one Play Right, use the "Add additional Play Right" button, and fill in the desired attributes for each Play Right.

When consuming a license, the client uses the first Play Right for which it meets all the requirements. Multiple play rights may be used to specify different restrictions for different operating systems. For example, it is possible to specify one right with Output Protection required for Windows (by blacklisting DRM versions on Macintosh and Linux) and to specify a second right with Output Protection "Use if available" on other platforms (by blacklisting DRM versions on Windows). 
