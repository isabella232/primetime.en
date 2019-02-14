---
description: The content of a PTAdAsset describes a companion banner.
seo-description: The content of a PTAdAsset describes a companion banner.
seo-title: Companion banner data
title: Companion banner data
uuid: c61f9ae6-f93a-4ff3-9c22-a33328c54281
---

# Companion banner data {#companion-banner-data}

The content of a PTAdAsset describes a companion banner.

<!--<a id="section_D730B4FD6FD749E9860B6A07FC110552"></a>-->

The `PTMediaPlayerAdStartedNotification` notification returns a `PTAd` instance that contains a `companionAssets` property (array of `PtAdAsset`). 
Each `PtAdAsset` provides information about displaying the asset. 

<table id="table_760C885E2DCA4BE983CC57FDA7BD5B14"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"><b>Available information</b></th> 
   <th colname="col2" class="entry"><b>Description</b></th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> width </td> 
   <td colname="col2"> Width of the companion banner in pixels. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> height </td> 
   <td colname="col2"> Height of the companion banner in pixels. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> resource type </td> 
   <td colname="col2">The resource type for this companion banner: 
    <ul id="ul_A067787FE49E4B6095BE0AC1D447DBB3"> 
     <li id="li_02B7224C67004095B3F6E50FD21E507E">html: The data is in HTML code. </li> 
     <li id="li_5F37E14472424F808C6094F42009E676">iframe: The data is an iframe URL (src). </li> 
     <li id="li_76B945007CE842158B5125422765E0B2">static: The data is a staticURL that is a direct URL to an image. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> data </td> 
   <td colname="col2"> The data of the type that is specified by <span class="codeph">resourceType</span> for this companion banner. </td> 
  </tr> 
 </tbody> 
</table>