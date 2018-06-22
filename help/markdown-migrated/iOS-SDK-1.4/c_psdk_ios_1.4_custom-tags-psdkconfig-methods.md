---
description: You can configure custom tag names in globally with the PTSDKConfig class. Q: Double-check whether iOS also has the stream-based method. There's no MediaPlayerItemConfig in Android.
seo-description: You can configure custom tag names in globally with the PTSDKConfig class. Q: Double-check whether iOS also has the stream-based method. There's no MediaPlayerItemConfig in Android.
seo-title: Config class methods for tags
title: Config class methods for tags
---

# Config class methods for tags

applies the global configuration automatically to any media stream that does not specify a stream-specific configuration.

<table id="table_B37A6C75270D47BC99258F2884AD6905"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="*" /> 
  <colspec colnum="2" colname="col2" colwidth="*" /> 
  <tbody> 
   <tr> 
    <td namest="col1" nameend="col2"><b>Subscribe to specific custom tags</b> </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">subscribedTags</span> </td> 
    <td colname="col2"> Retrieves the current list of subscribed tags. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">setSubscribedTags</span> </td> 
    <td colname="col2"> Sets the list of subscribed tags that will be exposed to the application. </td> 
   </tr> 
   <tr> 
    <td namest="col1" nameend="col2"><b>Customize the ad tags used by the default opportunity detector </b> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph">adTags</span> </td> 
    <td colname="col2"> Retrieves the current list of ad tags. </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph">setAdTags</span> </td> 
    <td colname="col2"> Sets the list of ad tags that will be used by default opportunity generator. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

`codeph PTSDKConfig` exposes these methods to manage the custom tags:

Remember the following:
* The setter methods do not allow the tags parameter to contain null values.
* The custom tag name must contain the # prefix.
  For example, #EXT-X-ASSET is a correct custom tag name, but EXT-X-ASSET is incorrect.
  
  
* You cannot change the configuration after the media stream has been loaded.

