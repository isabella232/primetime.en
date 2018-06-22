---
---

[com.adobe.mediacore.qos](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/package-detail.html)
[com.adobe.mediacore.qos.metrics](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/metrics/package-detail.html)
<table frame="all" colsep="1" rowsep="1" id="table_2893EFF9755149159A4F94E781C76B6E"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="24*" /> 
  <colspec colnum="2" colname="2" colwidth="76*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Name </th> 
    <th colname="2" class="entry">Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/metrics/BufferingMetrics.html" format="html" scope="external">BufferingMetrics</a></span></td> 
    <td colname="2">Provides information about how much time the player spent while buffering and how often a buffering event occurred. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/DeviceInformation.html" format="html" scope="external">DeviceInformation</a></span></td> 
    <td colname="2">Provides information about the platform and operating system on which the 
     <ph conkeyref="phrases/primetime-sdk-name">
      Phrase
     </ph> runs: 
     <ul id="ul_0DE69F3B38E84964AB98DCCD11E5E123"> 
      <li id="li_19B2D1889FCA4B0F8FCB0EE8F87353B2">Version of the platform OS </li> 
      <li id="li_CA35F4A48FD34555AC7D7832D5997AD4">Version number of the 
       <ph conkeyref="phrases/primetime-sdk-name">
        Phrase
       </ph> library </li> 
      <li id="li_30D38320C2A3440E92C0A477FFFBF9A0">Device's model name </li> 
      <li id="li_2D15164B987E405685B96A900EBF041D">Device manufacturer’s name </li> 
      <li id="li_B78485CB9580444DB9694404706BA191">Dehvice UUID </li> 
      <li id="li_841EA77499B44F0692192F9DE1A798E4">Width/height of the device screen </li> 
     </ul> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/LoadInformation.html" format="html" scope="external"> LoadInformation</a></span> </td> 
    <td colname="2"> Contains various QoS information about loading various resources (files, manifest or playlist, fragments/segments, tracks, and so on). </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/LoadInformationType.html" format="html" scope="external"> LoadInformationType</a></span> </td> 
    <td colname="2"> Enumeration class that lists possible values for the type property of LoadInformation objects. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/PlaybackInformation.html" format="html" scope="external">PlaybackInformation</a></span> </td> 
    <td colname="2">Provides information on how the playback is performing. This includes the frame rate, the profile bit rate, the total time spent in buffering, the number of buffering attempts, the time it took to get the first byte from the first video fragment, the time it took to render the first frame, the currently buffered length, and the buffer time. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/metrics/PlaybackLoadMetrics.html" format="html" scope="external">PlaybackLoadMetrics</a></span></td> 
    <td colname="2">Provides information on how much time it took for the media to load, how much it took for the player to render the first frame or, in case of an error, to fail. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/metrics/PlaybackMetrics.html" format="html" scope="external">PlaybackMetrics</a></span> </td> 
    <td colname="2">Provides information on how the playback is behaving. This includes the frame rate, bit rate, buffer length, and so on. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/metrics/PlaybackSessionMetrics.html" format="html" scope="external">PlaybackSessionMetrics</a></span> </td> 
    <td colname="2">Provides information on how many seconds the player spent while actually playing and how much time the video was actually on screen. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/qos/QOSProvider.html" format="html" scope="external">QOSProvider</a></span></td> 
    <td colname="2">
     <ph>
      Provides essential QoS metrics for both playback and the device.
     </ph>
     <ph>
      QOS information provider class.
     </ph> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

