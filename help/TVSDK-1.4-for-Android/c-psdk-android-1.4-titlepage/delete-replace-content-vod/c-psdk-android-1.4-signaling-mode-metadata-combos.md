---
description: You can mark, delete, and replace time ranges in VOD streams by using different ad signaling mode and ad metadata combinations. Different combinations of signaling mode and metadata result in different behaviors.
seo-description: You can mark, delete, and replace time ranges in VOD streams by using different ad signaling mode and ad metadata combinations. Different combinations of signaling mode and metadata result in different behaviors.
seo-title: Effect on ad insertion and deletion from ad signaling mode and ad metadata combinations
title: Effect on ad insertion and deletion from ad signaling mode and ad metadata combinations
uuid: 4c9e8ff6-980c-4ed5-aeab-45ffd67c43ef
index: y
internal: n
snippet: y
---

# Effect on ad insertion and deletion from ad signaling mode and ad metadata combinations{#effect-on-ad-insertion-and-deletion-from-ad-signaling-mode-and-ad-metadata-combinations}

You can mark, delete, and replace time ranges in VOD streams by using different ad signaling mode and ad metadata combinations. Different combinations of signaling mode and metadata result in different behaviors.

>[!NOTE]
>
>When there is a conflict between time ranges and ad signaling modes, TVSDK gives the time ranges priority.

#### Signaling Mode / Metadata Combination Behaviors
<table>  
 <thead> 
  <tr> 
   <th class="entry"> Ad Signaling Mode </th> 
   <th class="entry"> Ad Metadata </th> 
   <th class="entry"> Resolvers Created </th> 
   <th class="entry"><span class="codeph"> PlacementInformations</span> created </th> 
   <th class="entry"> Resulting behavior </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colspan="5"> Server Map </td> 
  </tr> 
  <tr> 
   <td> </td> 
   <td> Delete </td> 
   <td> Delete </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE)</span> </td> 
   <td> Ranges deleted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Delete, Auditude </td> 
   <td> Delete, Auditude </td> 
   <td> 
    <ul> 
     <li><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE), </span> </li> 
     <li><span class="codeph"> PlacementInfo (Type.SERVER_MAP, Mode.INSERT)</span> </li> 
    </ul> </td> 
   <td> Ranges deleted, Ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Auditude </td> 
   <td> Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.SERVER_MAP, Mode.INSERT)</span> </td> 
   <td> Ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Replace, Auditude </td> 
   <td> Delete, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE), PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.REPLACE)</span> </td> 
   <td> Ranges replaced </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Mark </td> 
   <td> CustomAd </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.MARK)</span> </td> 
   <td> Ranges marked </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Mark, Auditude </td> 
   <td> CustomAd, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.MARK)</span> </td> 
   <td> Ranges marked, no ads inserted </td> 
  </tr> 
  <tr> 
   <td colspan="5"> Manifest Cues </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Auditude </td> 
   <td> Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.PRE_ROLL, Mode.INSERT)</span> </td> 
   <td> Ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Delete, Auditude </td> 
   <td> Delete, Auditude </td> 
   <td> 
    <ul> 
     <li><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE)</span> </li> 
     <li><span class="codeph"> PlacementInfo (Type.PRE_ROLL, Mode.INSERT)</span> </li> 
    </ul> </td> 
   <td> Ranges deleted, ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Mark, Auditude </td> 
   <td> Mark, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.MARK)</span> </td> 
   <td> Ranges marked, no ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Delete </td> 
   <td> Delete </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE)</span> </td> 
   <td> Ranges deleted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Mark </td> 
   <td> CustomAd </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.MARK)</span> </td> 
   <td> Ranges marked </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Replace, Auditude </td> 
   <td> Delete, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE), PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.REPLACE)</span> </td> 
   <td> Ranges replaced </td> 
  </tr> 
  <tr> 
   <td colspan="5"> Custom Time Range </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Delete </td> 
   <td> Delete </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE)</span> </td> 
   <td> Ranges deleted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Delete, Auditude </td> 
   <td> Delete, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE)</span> </td> 
   <td> Ranges deleted, no ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Auditude </td> 
   <td> Auditude </td> 
   <td> None </td> 
   <td> No ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Replace, Auditude </td> 
   <td> Delete, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE), PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.REPLACE)</span> </td> 
   <td> Ranges replaced with ads </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Mark </td> 
   <td> CustomAd </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.MARK)</span> </td> 
   <td> Ranges marked </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Mark, Auditude </td> 
   <td> Custom Ad, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.MARK)</span> </td> 
   <td> Ranges marked, no ads inserted </td> 
  </tr> 
  <tr> 
   <td colspan="5"> Not set (default) </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Delete </td> 
   <td> Delete </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE)</span> </td> 
   <td> Ranges deleted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Delete, Auditude </td> 
   <td> Delete, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE), PlacementInfo (Type.SERVER_MAP, Mode.INSERT)</span> </td> 
   <td> Ranges deleted, ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Auditude </td> 
   <td> Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.SERVER_MAP, Mode.INSERT)</span> </td> 
   <td> Ads inserted </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Replace, Auditude </td> 
   <td> Delete, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.DELETE), PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.REPLACE)</span> </td> 
   <td> Ranges replaced with ads </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Mark </td> 
   <td> CustomAd </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.MARK)</span> </td> 
   <td> Ranges marked </td> 
  </tr> 
  <tr> 
   <td></td> 
   <td> Mark, Auditude </td> 
   <td> CustomAd, Auditude </td> 
   <td><span class="codeph"> PlacementInfo (Type.CUSTOM_TIME_RANGE, Mode.MARK)</span> </td> 
   <td> Ranges marked </td> 
  </tr> 
 </tbody> 
</table>

