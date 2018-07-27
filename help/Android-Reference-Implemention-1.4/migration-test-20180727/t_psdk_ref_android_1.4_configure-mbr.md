---
description: You can set initial, minimum, and maximum bit rate as well as the adaptive bit rate (ABR) switch policy for a multiple bit rate (MBR) stream.
seo-description: You can set initial, minimum, and maximum bit rate as well as the adaptive bit rate (ABR) switch policy for a multiple bit rate (MBR) stream.
seo-title: Enable adaptive bit rate
title: Enable adaptive bit rate
uuid: 4fcffe05-2652-4fee-be42-b205f2957989
index: n
internal: n
snippet: y
translate: y
---

# Enable adaptive bit rate

The  can play video assets that have multiple bit rates to provide more than one quality level based on the bandwidth and the quality of the playback.  automatically switches to the bit rate the provides the best playback experience. The reference implementation configures the following ABR parameters. 

<table id="table_3BB964A9F54B44339AECA790DDBD6C50"> 
 <tbody> 
  <tr> 
   <td colname="col1">initial bit rate</td> 
   <td colname="col2">The bit rate profile with which the video playback starts. If none of the profiles match, the 
    <ph conref="../../phrase_library.xml#c_psdk_phrase-library/primetime-sdk-name" /> chooses the one that is closest. If this is lower than the minimum bit rate or 0, the 
    <ph conref="../../phrase_library.xml#c_psdk_phrase-library/primetime-sdk-name" /> follows the ABR policy (see below). If this is higher than the maximum bit rate, the PDSK chooses the maximum bit rate. </td> 
  </tr> 
  <tr> 
   <td colname="col1">minimum bit rate</td> 
   <td colname="col2">This is the lowest bit rate profile to which the ABR can switch.</td> 
  </tr> 
  <tr> 
   <td colname="col1">maximum bit rate</td> 
   <td colname="col2">This is the highest bit rate profile to which the ABR can switch.</td> 
  </tr> 
  <tr> 
   <td colname="col1">ABR policy</td> 
   <td colname="col2">You can set one of three policies for ABR switching. <p> 
     <ul id="ul_53BF29B294E140419E1E8F88E5E91BF0"> 
      <li id="li_10ED3E4AB55F470F84A71B7FBD5AD821">conservative: Starts at the lowest bit rate, switches to the higher bit rate profile when the bandwidth is 50% higher than the current bit rate profile.</li> 
      <li id="li_02A2CE1E61FA48BDA868F2C24CB296FE">median: Starts at the median bit rate, switches to the higher bit rate profile when the bandwidth is 20% higher than the current bit rate profile.</li> 
      <li id="li_97F2DA7C8DAB4A81A47A3FCE1D3D2D2B">aggressive: Starts at the highest bit rate and always switches to the higher bit rate profile when possible.</li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>


>1. Step
