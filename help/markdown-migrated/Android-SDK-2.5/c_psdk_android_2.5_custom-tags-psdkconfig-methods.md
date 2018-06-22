---
description: You can globally configure custom tag names in with the MediaPlayerItemConfig class.
seo-description: You can globally configure custom tag names in with the MediaPlayerItemConfig class.
seo-title: Config class methods for tags
title: Config class methods for tags
---

# Config class methods for tags

automatically applies the global configuration to any media stream that does not specify a stream-specific configuration.

<table id="table_B37A6C75270D47BC99258F2884AD6905"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="*" /> 
  <colspec colnum="2" colname="col2" colwidth="*" /> 
  <tbody> 
   <tr> 
    <td namest="col1" nameend="col2"> <b>Subscribe to specific custom tags</b> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> public final String[] getSubscribedTags </span> </td> 
    <td colname="col2"> <p>Retrieves the current list of subscribed tags.</p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> public final void setSubscribedTags(String[] tags); </span> </td> 
    <td colname="col2"> <p>Sets the list of subscribed tags that will be exposed to the application.</p> <p>Your application is also automatically subscribed to all tags transmitted through <span class="codeph"> setAdTags </span>. </p> </td> 
   </tr> 
   <tr> 
    <td namest="col1" nameend="col2"> <b>Customize the ad tags used by the default opportunity detector</b> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> public final String[] getAdTags; </span> </td> 
    <td colname="col2"> <p>Retrieves the current list of ad tags.</p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <span class="codeph"> public final void setAdTags(String[] tags); </span> </td> 
    <td colname="col2"> <p>Sets the list of ad tags that will be used by default opportunity generator.</p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

`codeph  MediaPlayerItemConfig` exposes these methods to manage the custom tags:

Remember the following:
* The setter methods do not allow the tags parameter to contain null values.
  If encountered,  throws an `codeph  IllegalArgumentException`.
  
  
* The custom tag name must contain the `codeph  #` prefix.
  For example, `codeph  #EXT-X-ASSET` is a correct custom tag name, but `codeph  EXT-X-ASSET` is incorrect.
  
  
* You cannot change the configuration after the media stream has been loaded.

