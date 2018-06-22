---
---

<a id="section_E5D37C71323947E2AED8B866D9835E31"></a>

Use the following API elements to change play rates:
* `codeph  PlaybackRateEvent.getRate`
* `codeph  MediaPlayerEvent.RATE_SELECTED`
* `codeph  MediaPlayerEvent.RATE_PLAYING`
* `codeph  MediaPlayerItem.isTrickPlaySupported`
* `codeph  MediaPlayerItem.getAvailablePlaybackRates`, which specifies valid rates.

<table id="table_198E21AAFB794A0D938C9404157ED88C"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.12*" /> 
  <colspec colnum="2" colname="col2" colwidth="1.00*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Rate value </th> 
    <th colname="col2" class="entry"> Effect on playback </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> 2.0, 4.0, 8.0, 16.0, 32.0, 64.0, 128.0 </td> 
    <td colname="col2"> Switches to fast-forward mode with the specified multiplier faster than normal (for example, 4 is 4 times faster than normal) </td> 
   </tr> 
   <tr> 
    <td colname="col1"> -2.0, -4.0, -8.0, -16.0, -32.0, -64.0 , -128.0 </td> 
    <td colname="col2"> Switches to fast-rewind mode </td> 
   </tr> 
   <tr> 
    <td colname="col1"> 1.0 </td> 
    <td colname="col2"> Switches to normal play mode (calling <span class="codeph"> play </span> is the same as setting the rate property to 1.0) </td> 
   </tr> 
   <tr> 
    <td colname="col1"> 0.0 </td> 
    <td colname="col2"> Pauses (calling <span class="codeph"> pause </span> is the same as setting the rate property to 0.0) </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>



