---
seo-title: Details for the NATIVE_ERROR notification
title: Details for the NATIVE_ERROR notification
uuid: 33fde237-a3dd-44df-8e8a-4fcf0924e234
index: y
internal: n
snippet: y
translate: y
---

# Details for the NATIVE_ERROR notification

When TVSDK handles a native error, it returns some or all of the following metadata key values as strings. 

<table id="table_7F713B7A56024D8DA3C84E449D09CC91"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metadata key name </th> 
   <th colname="col2" class="entry"> Metadata value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="codeph"> NATIVE_ERROR_CODE</span> </td> 
   <td colname="col2"> <p>Native error code from the AVE. </p> <p>These codes represent the following: 
     <ul id="ul_1F33D523DDFE4CE8B4F0DC279FF7E4F8"> 
      <li id="li_07A2D9BEE6364935A61EF3BD4AB6DE27">DRM errors (codes 3300 to 3367). These are the same as the equivalent Flash Player error codes </li> 
      <li id="li_433BA22DE3504AEEB623598BB4F939FA">Video playback errors (-1 to 89) </li> 
      <li id="li_B347CB151DB94DE0A1DDEB1B33D2DABA">Cryptography errors (300 to 307) </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> NATIVE_ERROR</span> </td> 
   <td colname="col2">Short description of the notification (for example, <span class="codeph"> AAXS_InvalidVoucher</span> or <span class="codeph"> DECODER_FAILED</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> DESCRIPTION</span> </td> 
   <td colname="col2"> Long description of the notification (for example, Ad resolving operation has failed). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> PSDK_ERROR_CODE</span> </td> 
   <td colname="col2"><span class="codeph"> com.adobe.mediacore.PSDKErrorCode</span> numeric value as a string (for example, "13"). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> PSDK_ERROR</span> </td> 
   <td colname="col2"><span class="codeph"> com.adobe.mediacore.PSDKErrorCode</span> as a string (for example, <span class="codeph"> kECNetworkError</span>). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> WARNING</span> </td> 
   <td colname="col2"> Description of the warning. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> ERROR</span> </td> 
   <td colname="col2"> Description of the error. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>DRM</b> </td> 
   <td colname="col2"></td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> NATIVE_SUBERROR_CODE</span> </td> 
   <td colname="col2"> Minor error from the DRM module. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> DRM_ERROR_STRING</span> </td> 
   <td colname="col2"> Description of the error. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> DRM_ERROR_SERVER_URL</span> </td> 
   <td colname="col2"> URL of the DRM server to which TVSDK tried to talk. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Ad manifest load failure</b> </td> 
   <td colname="col2"></td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> AD_URL</span> </td> 
   <td colname="col2"> URL of the content that failed to load. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> AD_TYPE</span> </td> 
   <td colname="col2">Type of ad (a constant from the <span class="codeph"> MediaResource.Type</span> enum). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> AD_DURATION</span> </td> 
   <td colname="col2"> Ad duration in milliseconds. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> AD_ID</span> </td> 
   <td colname="col2"> ID assigned to the ad. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>File errors</b> </td> 
   <td colname="col2"></td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> DOWNLOAD_ERROR</span> </td> 
   <td colname="col2"> Description of the error during media file download. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> URL</span> </td> 
   <td colname="col2"> URL of file being downloaded. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> MANIFEST_ERROR</span> </td> 
   <td colname="col2"> Description of error during manifest file download. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> CONTENT_ERROR</span> </td> 
   <td colname="col2">Description of error during fragment (for example, <span class="codeph"> ts</span>) download. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Audio track errors</b> </td> 
   <td colname="col2"></td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> AUDIO_TRACK_NAME</span> </td> 
   <td colname="col2"> Name of the audio track that failed to load, as specified in the manifest. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> AUDIO_TRACK_LANGUAGE</span> </td> 
   <td colname="col2"> Language of the audio track, as specified in the manifest. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Seek errors</b> </td> 
   <td colname="col2"></td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> DESIRED_SEEK_PERIOD</span> </td> 
   <td colname="col2"> ID of the period (integer). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> DESIRED_SEEK_POSITION</span> </td> 
   <td colname="col2"> <p>Position (in milliseconds) sought (double). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Miscellaneous</b> </td> 
   <td colname="col2"></td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="codeph"> AUDITUDE_ERROR_CODE</span> </td> 
   <td colname="col2"> Auditude error code (number). </td> 
  </tr> 
 </tbody> 
</table>

