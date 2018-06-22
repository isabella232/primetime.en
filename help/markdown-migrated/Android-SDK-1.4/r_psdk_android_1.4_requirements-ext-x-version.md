---
---

<a id="section_8850183988124049A001758F117AD3A6"></a>

Here is some information about the `codeph  #EXT-X-VERSION` tag, which specifies the HLS protocol version:

* The version must match the features and attributes in the HLS playlist; otherwise, playback errors might occur.
  For more information, see [ HTTP Live Streaming specification ](https://datatracker.ietf.org/doc/draft-pantos-http-live-streaming/?include_text=1).
  
  
* The version must match the features and attributes in the HLS playlist; otherwise, playback errors might occur.
  For more information, see [ HTTP Live Streaming specification ](https://datatracker.ietf.org/doc/draft-pantos-http-live-streaming/?include_text=1).
  
  
* Adobe recommends using at least version 2 for playback in -based clients.
<table frame="all" colsep="1" rowsep="1" id="table_62EB98EDD9DE49EC84CB1C7D59BC40E6"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="26*" /> 
  <colspec colnum="2" colname="2" colwidth="74*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry"> Use at least this version </th> 
    <th colname="2" class="entry"> To use these features </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> EXT-X-VERSION:2 </span> </td> 
    <td colname="2"> The IV attribute of the <span class="codeph"> EXT-X-KEY </span> tag. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> <span class="codeph"> EXT-X-VERSION:3 </span> </td> 
    <td colname="2"> 
     <ul id="ul_C9500D3F934848639C204BF248F139FF"> 
      <li id="li_535A7E3FABCB46FE872A7EA5DE2A1784">Floating-point <span class="codeph"> EXTINF </span> duration values <p>The duration tags ( <span class="codeph"> #EXTINF: </span>&lt;duration&gt;,&lt;title&gt;) in version 2 were rounded to integer values. Version 3 and above require durations to be exact in floating point. </p> </li> 
     </ul> </td> 
   </tr> 
   <tr rowsep="0"> 
    <td colname="1"> <p> <span class="codeph"> EXT-X-VERSION:4 </span> </p> </td> 
    <td colname="2"> <p> 
      <ul id="ul_642834D8F1A64F5682B7B8E71D0F522A"> 
       <li id="li_2FD4DBB5381E475ABE62161647EAB0C3">The <span class="codeph"> EXT-X-BYTERANGE </span> tag </li> 
       <li id="li_47C712DCD4E3417180B3135A3E0AD742">The <span class="codeph"> EXT-X-I-FRAME-STREAM-INF </span> tag </li> 
       <li id="li_70A264713EE74078BAAB3CA95ACF8FAF">The <span class="codeph"> EXT-X-I-FRAMES-ONLY </span> tag </li> 
       <li id="li_BC4A80A0C30847BEAEA508D8A735A71A">The <span class="codeph"> EXT-X-MEDIA </span> tag </li> 
       <li id="li_46742583C61F4EBE89111BF3454D75F0">The <span class="codeph"> AUDIO </span> and <span class="codeph"> VIDEO </span> attributes of the <span class="codeph"> EXT-X-STREAM-INF </span> tag </li> 
       <li id="li_7CCEFD4E49264B3CB3800AC408F37817"> 
        <ph conkeyref="phrases/primetime-sdk-name" /> alternate audio </li> 
      </ul> </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

  Clients and servers must implement the versions in the following way:
  
  
