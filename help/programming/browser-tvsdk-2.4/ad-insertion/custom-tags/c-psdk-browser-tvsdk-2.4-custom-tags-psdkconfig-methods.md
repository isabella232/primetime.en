---
description: You can configure custom tag names in a stream with the MediaPlayerItemConfig class.
seo-description: You can configure custom tag names in a stream with the MediaPlayerItemConfig class.
seo-title: Config class methods for tags
title: Config class methods for tags
uuid: 222a0349-58d5-4bf3-9d03-e5920610faf5
---

# Config class methods for tags{#config-class-methods-for-tags}

You can configure custom tag names in a stream with the MediaPlayerItemConfig class.

To create a new `MediaPlayerItemConfig`: 

```js
var mediaPlayerItemConfig = new AdobePSDK.MediPlayerItemConfig();
```

Here is some information about how the `MediaPlayerItemConfig` methods are used to manage custom tags:  

<table id="table_0AC0973497144DDAB05726E3F031ACD1"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Subscribe to specific custom tags</b> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      var&amp;nbsp;subscribeTagsObtained&amp;nbsp;=&amp;nbsp;mediaPlayerItemConfig.subscribeTags;
    </code> </td> 
   <td colname="col2"> <p>Retrieves the current list of subscribed tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      var&nbsp;subscribeTags&nbsp;=&nbsp;["#EXT-X-PROGRAM-DATE-TIME"];mediaPlayerItemConfig.subscribeTags&nbsp;=&nbsp;subscribeTags;
    </code> </td> 
   <td colname="col2"> <p>Sets the list of subscribed tags exposed to the application. </p> <p>Your application is also automatically subscribed to all tags that are transmitted through <span class="codeph"> adTags </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Customize the ad tags used by the default opportunity detector </b> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      var&amp;nbsp;adTagsObtained&amp;nbsp;=&amp;nbsp;mediaPlayerItemConfig.adTags; 
    </code> </td> 
   <td colname="col2"> <p>Retrieves the current list of ad tags. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      var&nbsp;adTags&nbsp;=&nbsp;["#EXT-X-CUE"];mediaPlayerItemConfig.adTags&nbsp;=&nbsp;adTags;
    </code> </td> 
   <td colname="col2"> <p>Sets the list of ad tags to be used by the default opportunity generator. </p> </td> 
  </tr> 
 </tbody> 
</table>

Remember the following:

* The custom tag name must contain the `#` prefix.

  For example, `#EXT-X-ASSET` is a correct custom tag name, but `EXT-X-ASSET` is incorrect. 

* You cannot change the configuration after the media stream has been loaded.

