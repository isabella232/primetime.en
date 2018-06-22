---
description: The can play videos that have multiple profiles with different bit rates, switching between them to provide more than one quality level based on the available bandwidth. WRITER: Note that the text here is nearly identical to the text in c_psdk_abr-control-quality.xml. So if you update here, please update there, too. Or figure out a good way to put the text into the phrase library. Or maybe not--this file doesn't appear anywhere except in the original android, android_1.2, and the original dhls ditamaps. So I think it's basically obsolete. -elf Sept '15
seo-description: The can play videos that have multiple profiles with different bit rates, switching between them to provide more than one quality level based on the available bandwidth. WRITER: Note that the text here is nearly identical to the text in c_psdk_abr-control-quality.xml. So if you update here, please update there, too. Or figure out a good way to put the text into the phrase library. Or maybe not--this file doesn't appear anywhere except in the original android, android_1.2, and the original dhls ditamaps. So I think it's basically obsolete. -elf Sept '15
seo-title: Multiple bit rates
title: Multiple bit rates
---

# Multiple bit rates

You can set initial, minimum, and maximum bit rates as well as the adaptive bit-rate (ABR) switch policy for a multiple bit rate (MBR) stream. The  automatically switches to the bit rate that provides the best playback experience within the specified configuration.

<table id="table_3BB964A9F54B44339AECA790DDBD6C50"> 
 <tgroup cols="2"> 
  <colspec colname="col01" colnum="1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="3.45*" /> 
  <tbody> 
   <tr> 
    <td colname="col01">Initial bit rate: <p><span class="codeph">getABRInitialBitRate</span> </p> </td> 
    <td colname="col2">The desired playback bit rate (in bits per second) for the first segment. When playback starts, the closest profile (equal to or greater than the initial bit rate) is used for the first segment. <p> If a minimum bit rate is defined and the initial bit rate is lower than the minimum, the 
      <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/primetime-sdk-name">
       Phrase
      </ph> selects the profile with the lowest bit rate above the minimum bit rate. Similarly, if the initial rate is above the maximum rate, the 
      <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/primetime-sdk-name">
       Phrase
      </ph> selects the highest rate below the maximum. If the initial bit rate is zero or undefined, the initial bit rate is determined by the ABR policy. </p><p>Returns an integer value that represents the byte-per-second profile. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col01">Minimum bit rate: <p><span class="codeph">getABRMinBitRate</span></p> </td> 
    <td colname="col2">The lowest allowed bit rate to which the ABR can switch. ABR switching ignores profiles with a bit rate lower than this. <p>Returns an integer value that represents the bits-per-second profile. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col01">Maximum bit rate: <p><span class="codeph">getABRMaxBitRate</span> </p> </td> 
    <td colname="col2">The highest allowed bit rate to which the ABR can switch. ABR switching ignores profiles with a bit rate higher than this. <p>Returns an integer value that represents the bits-per-second profile. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col01">ABR switching policy: <p><span class="codeph">getABRPolicy</span></p> </td> 
    <td colname="col2">The playback switches gradually to the highest-bit-rate profile when possible. You can set the policy for ABR switching, which determines how quickly the 
     <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/primetime-sdk-name" /> switches between profiles. The default is Moderate. <p> 
      <ul id="ul_53BF29B294E140419E1E8F88E5E91BF0"> 
       <li id="li_10ED3E4AB55F470F84A71B7FBD5AD821">Conservative: Switches to the profile with the next higher bit rate when the bandwidth is 50% higher than the current bit rate. </li> 
       <li id="li_02A2CE1E61FA48BDA868F2C24CB296FE">Moderate: Switches to the next higher bit rate profile when the bandwidth is 20% higher than the current bit rate. </li> 
       <li id="li_97F2DA7C8DAB4A81A47A3FCE1D3D2D2B">Aggressive: Switches immediately to the highest bit-rate profile when the bandwidth is higher than the current bit rate </li> 
      </ul> </p> <p>If the initial bit rate is zero or not specified and a policy is specified, playback starts with the lowest bit-rate profile for Conservative, the profile closest to the median bit rate of available profiles for Moderate, and the highest bit-rate profile for Aggressive. </p><p>The policy works within the constraints of the minimum and maximum bit rates, if they are specified. </p><p>Returns the current setting from the <span class="codeph">ABRControlParameters</span> enum: 
      <ul id="ul_svm_zqn_gz"> 
       <li><span class="codeph">ABR_CONSERVATIVE</span></li> 
       <li><span class="codeph">ABR_MODERATE</span></li> 
       <li><span class="codeph">ABR_AGGRESSIVE</span></li> 
      </ul></p> <p>See also <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/ABRControlParameters.ABRPolicy.html" scope="external" format="html"><span class="apiname">ABRPolicy</span></a>. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

The reference implementation configures the following ABR parameters in [`apiname IPlaybackConfig`](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html).

>[!NOTE]
>
>* The  failover mechanism might override these settings, because the  favors a continuous playback experience over strictly respecting the control parameters.
>* When the bit rate changes, the  dispatches `codeph onProfileChanged` events in `codeph PlaybackEventListener`.
>
