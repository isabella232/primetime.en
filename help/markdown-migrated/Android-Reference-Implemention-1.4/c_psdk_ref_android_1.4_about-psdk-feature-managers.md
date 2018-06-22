---
description: 
seo-description: 
seo-title: Feature managers
title: Feature managers
---

# Feature managers

Feature managers provide a way for you to control individual features without traversing the entire  in search of code for one feature that could be scattered in multiple locations. Feature managers condense code into one class per feature. The feature managers wait for triggers from  events and then inform the class that uses the feature manager to handle the result. The feature manager provides the required information to the class.

The feature managers perform the following tasks:
* **Triggers features.** These are function calls to trigger a  feature. For example, `codeph PlaybackManager.play()` is called when the player application needs to start the video playback.
* **Listens to  events.** The feature manager needs to listen to  events to acquire information from the . For example, `codeph AdsManager` listens to  Ads events to be notified when ad breaks start.
* **Dispatches events to the handler. **After the feature managers receive and process the events from the , they notify the client side to handle the event. For example, after `codeph AdsManager` receives an ad break start event, it tells the player fragment to reflect this change in the UI (disable the scrub bar, show the ad overlay, etc.).

<table id="table_7BDB52705ECF437FBE475D6B215B7413"> 
 <tgroup cols="4">
  <colspec colnum="1" colname="col1" colwidth="1.55*" />
  <colspec colname="col02" colnum="2" colwidth="1.45*" />
  <colspec colnum="3" colname="col2" colwidth="4.03*" />
  <colspec colname="col3" colnum="4" colwidth="1.00*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Feature manager </th> 
    <th colname="col02" class="entry">Default file </th> 
    <th colname="col2" class="entry">Feature </th> 
    <th colname="col3" class="entry"> </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"><a href="c_psdk_ref_video-playback.xml">Video playback</a> </td> 
    <td colname="col02">PlaybackManager </td> 
    <td colname="col2">HLS playback and control, DVR playback and control, buffer control, and multi-bit rate handling. </td> 
    <td colname="col3">Required </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="c_psdk_ref_content-protection.xml">DRM content protection</a> </td> 
    <td colname="col02">DrmManager </td> 
    <td colname="col2">Content protection. </td> 
    <td colname="col3">Required </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="c_psdk_ref_ad-insertion.xml">Ad insertion</a> </td> 
    <td colname="col02">AdsManager </td> 
    <td colname="col2">Ad insertion, including 
     <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/auditude-name-long">
      Phrase
     </ph>, direct ad break, and custom ad break. </td> 
    <td colname="col3">Optional </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="c_psdk_ref_closed-captions.xml">Closed captions </a> </td> 
    <td colname="col02">CCManager </td> 
    <td colname="col2">Closed captioning and VTT subtitles. </td> 
    <td colname="col3">Optional </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="c_psdk_ref_late-binding-audio.xml">Late-binding audio</a> </td> 
    <td colname="col02">AAManager </td> 
    <td colname="col2">Late binding audio. </td> 
    <td colname="col3">Optional </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="t_psdk_ref_qos-statistics.xml">QoS</a> </td> 
    <td colname="col02">QosManager </td> 
    <td colname="col2">QoS statistics. </td> 
    <td colname="col3">Optional </td> 
   </tr> 
   <tr> 
    <td colname="col1">Entitlement </td> 
    <td colname="col02">EntitlementManager </td> 
    <td colname="col2">
     <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/auth-name" /> entitlement integration. </td> 
    <td colname="col3">Optional </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

The Primetime reference implementation includes the following feature managers:

The reference implementation contains basic default classes, listed above, and corresponding classes with the suffix of On. The default classes provide the default  behaviors while the classes with the On suffix include all the code required to trigger the  feature and listen to  events for that feature.

* For optional features, the default code operates as if the feature is turned off.
* Classes with the On suffix operate as if the feature is turned on.


