---
---

>The code block below defines the details JSON object when the type value is Primetime ads.
>
>
>
>```
>>“metadata”: {
> “ad” : {
> “type”: “Primetime ads”,
> “details”: {
> "domain": "sandbox2.auditude.com",
> "mediaid": "rom_asset_case_1",
> "zoneid": "109754",
> "targeting": [
> {
> "key": "osmfKeyMulAdsAvail12346",
> "value": "MulAdsAvail12346"
> }
> ]
> }
> }
>}
>
>```
>
>
><table id="table_5F364EF751CB49E7A640E6D58D0B03F7"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="3.85*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Property</th> 
    <th colname="col2" class="entry">Description</th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1">domain</td> 
    <td colname="col2">The Primetime ads domain to use for ad requests.</td> 
   </tr> 
   <tr> 
    <td colname="col1">mediaid</td> 
    <td colname="col2">The mediaid that has been set up in Primetime ads for this content.</td> 
   </tr> 
   <tr> 
    <td colname="col1">zoneid</td> 
    <td colname="col2">The Primetime ads zoneid. See the Primetime ads documentation for more information.</td> 
   </tr> 
   <tr> 
    <td colname="col1">targeting</td> 
    <td colname="col2">An array of key/value pairs used for targeting specific ads for the content.</td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
>
>
>See [com.adobe.mediacore.metadata.AuditudeSettings](http://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/metadata/AuditudeSettings.html) for more information on the value of these attributes.
>
>
