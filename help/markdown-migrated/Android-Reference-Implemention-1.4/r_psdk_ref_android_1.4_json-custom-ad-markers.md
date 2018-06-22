---
---

>The code block below defines the "details" JSON object when the type is custom ad markers.
>
>
>The MetadataNode returned by IFeedItemAdapter:getStreamMetadata() contains 2 entries - an entry with key of type com.adobe.mediacore.metadata.DefaultMetadataKeys.CUSTOM_AD_MARKERS_METADATA_KEY and value of of an instance of the MetadataNode returned by TimeRangeCollection.toMetadata(). The second entry has a key of type com.adobe.mediacore.metadata.DefaultMetadataKeys.METADATA_KEY_ADJUST_SEEK_ENABLED with the value of the "adjust-seek-position" attribute below.
>
>
>
>```
>>“metadata”: {
> “ad” : {
> “type”: “custom ad markers”,
> “details”: {
> "adjust-seek-position": true,
> "time-ranges": [
> {
> "begin": 5000,
> "end":15000
> },
> {
> "begin": 120000,
> "end":135000
> }
> ]
> }
> }
>}
>
>```
>
>
<table id="table_BBD08759C38C434B89CB1C429E64D1E9"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="3.85*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Property </th> 
    <th colname="col2" class="entry">Description </th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1">adjust-seek-position </td> 
    <td colname="col2">true or false, used to set the value of the key com.adobe.mediacore.metadata.DefaultMetadataKeys.METADATA_KEY_ADJUST_SEEK_ENABLED in the MetadataNode. </td> 
   </tr> 
   <tr> 
    <td colname="col1">time-ranges </td> 
    <td colname="col2">An array of JSON Objects indicating the time range for each ad marker. Each JSON Object entry maps to an instance of com.adobe.mediacore.utils.TimeRange. </td> 
   </tr> 
   <tr> 
    <td colname="col1">time-ranges.begin </td> 
    <td colname="col2">Value in ms indicating the start time of the ad marker. </td> 
   </tr> 
   <tr> 
    <td colname="col1">time-ranges.end </td> 
    <td colname="col2">Value in ms indicating the end time of the ad marker. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
>
>
>Refer to the  documentation for further information on how custom ad markers work.
>
>
