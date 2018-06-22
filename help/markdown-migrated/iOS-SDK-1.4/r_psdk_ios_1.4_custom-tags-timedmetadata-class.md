---
---

<table id="table_FFC56AC5B1E04DA99C9309C0223ABA90"> 
 <tgroup cols="3">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colname="col02" colnum="2" colwidth="1.66*" />
  <colspec colnum="3" colname="col2" colwidth="5.04*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Property</th> 
    <th colname="col02" class="entry">Type</th> 
    <th colname="col2" class="entry">Description</th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <span class="codeph">metadataId</span> </td> 
    <td colname="col02"><span class="codeph">NSString</span> </td> 
    <td colname="col2">Unique identifier of the timed metadata. This value is usually extracted from the cue/tag ID attribute. Otherwise, a unique random value is provided.</td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">name</span> </td> 
    <td colname="col02"><span class="codeph">NSString</span></td> 
    <td colname="col2"> The name of the timed metadata. If the type is <span class="codeph">TAG</span>, the value represents the cue/tag name. If the type is <span class="codeph">ID3</span>, it is null. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">time</span> </td> 
    <td colname="col02"><span class="codeph">CMTime</span></td> 
    <td colname="col2">The time position, in milliseconds, relative to the start of the main content where this timed metadata is present in the stream.</td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">type</span> </td> 
    <td colname="col02"> <span class="codeph">PTTimedMetadataType</span></td> 
    <td colname="col2">The type of the timed metadata. 
     <ul id="ul_70FBFB33E9F846D8B38592560CCE9560"> 
      <li id="li_739D30561BFB4D9B97DF212E4880BA2C">TAG - indicates that the timed metadata was created from a tag in the playlist/manifest.</li> 
      <li id="li_E785E1DEF1CC4D9DBE7764E5D05EFAFC">ID3 - indicates that the timed metadata was created from an ID3 tag in the media stream.</li> 
     </ul> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

<a id="section_737CC47997F74F80A3C5C6171ADE120E"></a>

Remember the following:
* automatically extracts the attributes list into key-value pairs and stores the attributes in the metadata property.
  >[!TIP]
  >
  >Complex data in custom tags in the manifest, such as strings with special characters, must be in quotes. For example:
  >```
  >#EXT-CUSTOM-TAG:type=SpliceOut,ID=1,time=71819.7222,duration=30.0,url=
  >"www.example.com:8090?parameter1=xyz&amp;parameter2=abc"
  >```
  >
  
* If the extraction fails because of a custom tag format, the content property always contains the tag's raw data, which is the string after the colon. No error is thrown in this case.
<table id="table_1BAE98BF23F641A3A5709EBE37B327F6"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="*" />
  <colspec colnum="2" colname="col2" colwidth="*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Element</th> 
    <th colname="col2" class="entry">Description</th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1">
     <ph>
      TAG, ID3
     </ph> </td> 
    <td colname="col2">Possible types for the timed metadata.</td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">@property (nonatomic, assign) CMTime time</span> </td> 
    <td colname="col2">The time position, relative to the start of the main content, where this metadata was inserted in the stream.</td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">@property (nonatomic, assign) PTTimedMetadataType type</span> </td> 
    <td colname="col2">Returns the type of the timed metadata.</td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">@property (nonatomic, retain) NSString *metadataId</span> </td> 
    <td colname="col2">Returns the ID extracted from the cue/tag attributes. Otherwise, a unique random value is provided.</td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">@property (nonatomic, retain) NSString *name</span> </td> 
    <td colname="col2">Returns the name of the cue, which is usually the HLS tag name.</td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

