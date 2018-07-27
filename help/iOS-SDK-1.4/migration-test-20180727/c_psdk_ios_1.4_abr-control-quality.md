---
description: HLS and DASH streams provide different bit rate encodings (profiles) for the same short burst of video. can select the quality level for each burst based on the available bandwidth.
seo-description: HLS and DASH streams provide different bit rate encodings (profiles) for the same short burst of video. can select the quality level for each burst based on the available bandwidth.
seo-title: Adaptive bit rates (ABR) for video quality
title: Adaptive bit rates (ABR) for video quality
uuid: dc9812e8-1385-4133-abcf-a79e5ba8dbb0
index: n
internal: n
snippet: y
translate: y
---

# Adaptive bit rates (ABR) for video quality

 <!-- PH element: phrases/primetime-sdk-name --> constantly monitors the bit rate to ensure that the content is played at the optimal bit rate for the current network connection.
You can set the adaptive bit-rate (ABR) switching policy and the initial, minimum, and maximum bit rates for a multiple-bit-rate (MBR) stream.  <!-- PH element: phrases/primetime-sdk-name --> automatically switches to the bit rate that provides the best playback experience in the specified configuration.

<table id="table_AF838E082235406AA359BF1C1A77F85F"> 
 <tbody> 
  <tr> 
   <td colname="col01">Initial bit rate</td> 
   <td colname="col2"> <p>The desired playback bit rate (in bits per second) for the first segment. When playback starts, the closest profile, which is equal to or greater than the initial bit rate, is used for the first segment.</p> <p> If a minimum bit rate is defined, and the initial bit rate is lower than the minimum rate, 
     <ph conkeyref="phrases/primetime-sdk-name" /> selects the profile with the lowest bit rate above the minimum bit rate. If the initial rate is above the maximum rate, 
     <ph conkeyref="phrases/primetime-sdk-name" /> selects the highest rate below the maximum rate. </p> <p>If the initial bit rate is zero or undefined, the initial bit rate is determined by the ABR policy.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col01">Minimum bit rate</td> 
   <td colname="col2"> <p>The lowest allowed bit rate to which the ABR can switch. ABR switching ignores profiles with a bit rate that is lower than this bit rate.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col01">Maximum bit rate</td> 
   <td colname="col2"> <p>The highest allowed bit rate to which the ABR can switch. ABR switching ignores profiles with a bit rate higher than this bit rate.</p> </td> 
  </tr> 
 </tbody> 
</table>

Keep the following information in mind: 
* <!-- PH element: phrases/primetime-sdk-name --> does not dispatch events from bit-rate switching.
* You can change your ABR settings at any time, and the player switches to use the profile that most closely matches the most recent settings.

For example, if a stream has the following profiles: 
* 1: 300000
* 2: 700000
* 3: 1500000
* 4: 2400000
* 5: 4000000
If you specify a range of 300000 to 2000000, <!-- PH element: phrases/primetime-sdk-name --> considers only profiles 1, 2 and 3. This allows applications to adjust to various network conditions, such as switching from WiFi to 3G or to various devices such as a phone, a tablet, or a desktop computer.
