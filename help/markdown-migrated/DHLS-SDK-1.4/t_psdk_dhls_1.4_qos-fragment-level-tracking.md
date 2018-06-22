---
description: You can read quality of service (QoS) information about downloaded resources, such as fragments and tracks, from the LoadInformation class.
seo-description: You can read quality of service (QoS) information about downloaded resources, such as fragments and tracks, from the LoadInformation class.
seo-title: Track at the fragment level using load information
title: Track at the fragment level using load information
---

# Track at the fragment level using load information

>1. Implement the `codeph  onLoadInformationAvailable` callback event listener.
>   ```
>   private function onLoadInformationAvailable(event:LoadInformationEvent):void { 
>    var loadInformation:LoadInformation = event.loadInformation; 
>    // process the load information here 
>   }
>   ```
>   
>   
>1. Register the event listener, which  calls every time a fragment has downloaded.
>       
>       ```
>       player.addEventListener(LoadInformationEvent.LOAD_INFORMATION_AVAILABLE, 
>        onLoadInformationAvailable);
>       ```
>       
>   
>1. Read the data of interest from the `codeph  LoadInformation` that is passed to the callback.
><table id="table_75E61A2EB25E435DB631166A7FF64757"> 
 <tgroup cols="3"> 
  <colspec colname="col01" colnum="1" colwidth="1.14*" /> 
  <colspec colnum="2" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="3" colname="col2" colwidth="1.44*" /> 
  <thead> 
   <tr> 
    <th colname="col01" class="entry"> Property </th> 
    <th colname="col1" class="entry"> Type </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col01"> <span class="codeph"> downloadDuration </span> </td> 
    <td colname="col1"> <p>Number</p> </td> 
    <td colname="col2"> <p>The duration of the download in milliseconds.</p> <p> 
      <ph conkeyref="phrases/primetime-sdk-name" /> does not differentiate between the time it took the client to connect to the server and the time it took to download the full fragment. For example, if a 10 MB segment takes 8 seconds to download, 
      <ph conkeyref="phrases/primetime-sdk-name" /> provides that information, but does not tell you that it took 4 seconds until the first byte and another 4 seconds to download the entire fragment. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col01"> <span class="codeph"> mediaDuration </span> </td> 
    <td colname="col1"> <p>Number</p> </td> 
    <td colname="col2"> The media duration of the downloaded fragments in milliseconds. </td> 
   </tr> 
   <tr> 
    <td colname="col01"> <span class="codeph"> size </span> </td> 
    <td colname="col1"> <p>Number</p> </td> 
    <td colname="col2"> The size of the downloaded resource in bytes. </td> 
   </tr> 
   <tr> 
    <td colname="col01"> <span class="codeph"> trackIndex </span> </td> 
    <td colname="col1"> <p>int</p> </td> 
    <td colname="col2"> The index of the corresponding track, if known; otherwise, 0. </td> 
   </tr> 
   <tr> 
    <td colname="col01"> <span class="codeph"> trackName </span> </td> 
    <td colname="col1"> <p>String</p> </td> 
    <td colname="col2"> The name of the corresponding track, if known; otherwise, null. </td> 
   </tr> 
   <tr> 
    <td colname="col01"> <span class="codeph"> trackType </span> </td> 
    <td colname="col1"> <p>String</p> </td> 
    <td colname="col2"> The type of the corresponding track, if known; otherwise, null. </td> 
   </tr> 
   <tr> 
    <td colname="col01"> <span class="codeph"> type </span> </td> 
    <td colname="col1"> <p>String</p> </td> 
    <td colname="col2"> What 
     <ph conkeyref="phrases/primetime-sdk-name" /> downloaded. One of the following: 
     <ul id="ul_FA02F42D109344F4866073908CA4E835"> 
      <li id="li_0E2D3EBCAB58477FB5EA526C54FACFFB">MANIFEST - A playlist/manifest</li> 
      <li id="li_D7894C2F0CB64C909C6398288EA5683A">FRAGMENT - A fragment</li> 
      <li id="li_4D4FEDB7704C411B80891B5028B0C20E">TRACK - A fragment associated with a specific track</li> 
     </ul> Sometimes it might not be possible to detect the type of the resource. If this occurs, FILE is returned. </td> 
   </tr> 
   <tr> 
    <td colname="col01"> <span class="codeph"> url </span> </td> 
    <td colname="col1"> <p>String</p> </td> 
    <td colname="col2"> The URL that points to the downloaded resource. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>   
>   
>   
>   
>   
