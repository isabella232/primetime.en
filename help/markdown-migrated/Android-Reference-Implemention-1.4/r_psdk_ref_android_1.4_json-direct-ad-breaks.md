---
---

>The following code block defines the details JSON object when the type value is direct ad breaks.
>
>
>The `codeph  MetadataNode` returned by `codeph  IFeedItemAdapter:getStreamMetadata()` contains an entry with key of type `codeph  com.adobe.mediacore.metadata.DefaultMetadataKeys.JSON_METADATA_KEY` and value of a string representation of the details JSON object value below.
>
>
>
>```
>>“metadata”: { 
> “ad” : { 
> “type”: “direct ad breaks”, 
> “details”: { 
> "ad-breaks": [ 
> { 
> "tag": "break-001", 
> "time": 0, 
> "replace": 0, 
> "ad-list": [ 
> { 
> }, 
> { 
> } 
> ] 
> }, 
> { 
> "tag": "break-002", 
> "time": 300000, 
> "replace": 0, 
> "ad-list": [ 
> { 
> } 
> ] 
> } 
> ] 
> } 
> } 
>} 
>
>```
>
>
><table id="table_4A1BCE4375C7406B8F3215E7D3FB3670"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="3.85*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Property </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <span class="codeph"> tag </span> </td> 
    <td colname="col2"> A string that maps to the tag field in <span class="codeph"> com.adobe.mediacore.timeline.advertising.AdBreak </span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> time </span> </td> 
    <td colname="col2"> Indicates the start time for the ad break, maps to the time field in <span class="codeph"> com.adobe.mediacore.timeline.advertising.AdBreak </span>. A value of 0 indicates a pre-roll ad. </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> replace </span> </td> 
    <td colname="col2"> Indicates the ad break replace duration, maps to the <span class="codeph"> replaceDuration </span> field in <span class="codeph"> com.adobe.mediacore.timeline.advertising.AdBreak </span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> ad-list </span> </td> 
    <td colname="col2"> A list of ads to be played during the given ad break, maps to the <span class="codeph"> List&lt;Ad&gt; </span> field in <span class="codeph"> com.adobe.mediacore.timeline.advertising.AdBreak </span>. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
>
>
>The following code block defines the JSON object for the ads-list array.
>
>
>
>```
>>"ad-list": [ 
> { 
> "url": "http://cdn.auditude.com/player/downloads/data/espn/ads/csx/prog_index.m3u8", 
> "duration": 15000, 
> "tag": "1st break - 1st ad" 
> }, 
> { 
> "url": "http://cdn.auditude.com/player/downloads/data/espn/ads/csx/prog_index.m3u8", 
> "duration": 30000, 
> "tag": "1st break - 2nd ad" 
> } 
>], 
>
>```
>
>
><table id="table_16DF81FEB31C4F9693CFDFA0884DE57F"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="3.85*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Property </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <span class="codeph"> url </span> </td> 
    <td colname="col2"> The URL to the ad content, maps to the url field in <span class="codeph"> com.adobe.mediacore.timeline.advertising.Ad </span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> duration </span> </td> 
    <td colname="col2"> The duration of the ad, maps to the duration field in <span class="codeph"> com.adobe.mediacore.timeline.advertising.Ad </span>. </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> tag </span> </td> 
    <td colname="col2"> A description string. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
>
>
