---
description: The TVSDK can play videos that have multiple profiles with different bit rates, switching between them to provide more than one quality level based on the available bandwidth.
seo-description: The TVSDK can play videos that have multiple profiles with different bit rates, switching between them to provide more than one quality level based on the available bandwidth.
seo-title: Multiple bit rates
title: Multiple bit rates
uuid: 46eac41e-0b2a-42e3-8a88-54ad9fe34212
index: y
internal: n
snippet: y
---

# Multiple bit rates{#multiple-bit-rates}

The TVSDK can play videos that have multiple profiles with different bit rates, switching between them to provide more than one quality level based on the available bandwidth.

 You can set initial, minimum, and maximum bit rates as well as the adaptive bit-rate (ABR) switch policy for a multiple bit rate (MBR) stream. The TVSDK automatically switches to the bit rate that provides the best playback experience within the specified configuration.

The reference implementation configures the following ABR parameters in [ <!-- APINAME - Required Post Migration Cleanup -->`IPlaybackConfig`](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html).  

<table id="table_3BB964A9F54B44339AECA790DDBD6C50"> 
 <tbody> 
  <tr> 
   <td colname="col01">Initial bit rate: <p><span class="codeph"> getABRInitialBitRate</span> </p> </td> 
   <td colname="col2">The desired playback bit rate (in bits per second) for the first segment. When playback starts, the closest profile (equal to or greater than the initial bit rate) is used for the first segment. <p> If a minimum bit rate is defined and the initial bit rate is lower than the minimum, the TVSDK selects the profile with the lowest bit rate above the minimum bit rate. Similarly, if the initial rate is above the maximum rate, the TVSDK selects the highest rate below the maximum. If the initial bit rate is zero or undefined, the initial bit rate is determined by the ABR policy. </p> <p>Returns an integer value that represents the byte-per-second profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01">Minimum bit rate: <p><span class="codeph"> getABRMinBitRate</span> </p> </td> 
   <td colname="col2">The lowest allowed bit rate to which the ABR can switch. ABR switching ignores profiles with a bit rate lower than this. <p>Returns an integer value that represents the bits-per-second profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01">Maximum bit rate: <p><span class="codeph"> getABRMaxBitRate</span> </p> </td> 
   <td colname="col2">The highest allowed bit rate to which the ABR can switch. ABR switching ignores profiles with a bit rate higher than this. <p>Returns an integer value that represents the bits-per-second profile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01">ABR switching policy: <p><span class="codeph"> getABRPolicy</span> </p> </td> 
   <td colname="col2">The playback switches gradually to the highest-bit-rate profile when possible. You can set the policy for ABR switching, which determines how quickly the TVSDK switches between profiles. The default is Moderate. <p> 
     <ul id="ul_53BF29B294E140419E1E8F88E5E91BF0"> 
      <li id="li_10ED3E4AB55F470F84A71B7FBD5AD821">Conservative: Switches to the profile with the next higher bit rate when the bandwidth is 50% higher than the current bit rate. </li> 
      <li id="li_02A2CE1E61FA48BDA868F2C24CB296FE">Moderate: Switches to the next higher bit rate profile when the bandwidth is 20% higher than the current bit rate. </li> 
      <li id="li_97F2DA7C8DAB4A81A47A3FCE1D3D2D2B">Aggressive: Switches immediately to the highest bit-rate profile when the bandwidth is higher than the current bit rate </li> 
     </ul> </p> <p>If the initial bit rate is zero or not specified and a policy is specified, playback starts with the lowest bit-rate profile for Conservative, the profile closest to the median bit rate of available profiles for Moderate, and the highest bit-rate profile for Aggressive. </p> <p>The policy works within the constraints of the minimum and maximum bit rates, if they are specified. </p> <p>Returns the current setting from the <span class="codeph"> ABRControlParameters</span> enum: 
     <ul id="ul_svm_zqn_gz"> 
      <li id="li_5D14B00DA3724729BE3C947C72CF38C9"><span class="codeph"> ABR_CONSERVATIVE</span> </li> 
      <li id="li_FC9D9BA68E3A44F3A0D788453E1C2CC8"><span class="codeph"> ABR_MODERATE</span> </li> 
      <li id="li_F12CCE8C91524D3190DB07C8E6E744F0"><span class="codeph"> ABR_AGGRESSIVE</span> </li> 
     </ul> </p> <p>See also <a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/ABRControlParameters.ABRPolicy.html" scope="external" format="html"><span class="apiname"> ABRPolicy</span></a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>* The TVSDK failover mechanism might override these settings, because the TVSDK favors a continuous playback experience over strictly respecting the control parameters. 
>* When the bit rate changes, the TVSDK dispatches `onProfileChanged` events in `PlaybackEventListener`. 
>

## Enabling custom ABR control in the reference implementation {#section_72A6E7263E1441DD8D7E0690285515E6}

Adaptive bit rate (ABR) is enabled in the TVSDK by default. You can use the Primetime Settings user interface to override the default TVSDK behavior in the reference implementation by configuring custom ABR control.

To enable custom ABR through the Settings user interface:

* Open the Primetime Settings dialog. 
* Select **[!UICONTROL ABR controls]**. 
  <a id="fig_A8170AF1727D48E19A2F45D730E5001E"></a>

  ![](assets/abr-configuration.jpg)

* Tap the Enable ON control so that it displays OFF.

>[!NOTE]
>
>The `PlaybackManager` only sets the ABR parameters if [isABRControlEnabled](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html) returns true (ON). If it returns false (OFF), the `PlaybackManager` uses the default ABR control so the initial, minimum, and maximum bit rates will all be 0 and the ABR policy will be `ABR_MODERATE`.

## Configure for low bit rates {#section_5451691CBBD24542AD54A474D222CD39}

For some low bit-rate playback rates, the TVSDK, by default, switches to the audio-only stream and the playback appears frozen. You can configure the player so that it never encounters a situation where it switches to audio-only.

* Implement the [IPlaybackConfig](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html) interface:

* Ensure that [getABRMinBitRate](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html#getABRMinBitRate()) is higher than the audio-only bit rate (higher than 64000). 
* Ensure that [isABRControlEnabled](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IPlaybackConfig.html#isABRControlEnabled()) is on.

