---
description: The MediaResource class represents the content to be loaded by the MediaPlayer instance.
seo-description: The MediaResource class represents the content to be loaded by the MediaPlayer instance.
seo-title: Create a media resource
title: Create a media resource
---

# Create a media resource

>1. Create a `codeph MediaResource` by passing information about the media to the `codeph MediaResource` constructor.
><table id="table_DD0D5D9129D54F73881399B9B4FF546A"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="2.99*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Constructor Parameter</th> 
    <th colname="col2" class="entry">Description</th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"><span class="codeph">url</span></td> 
    <td colname="col2"> <p>A string that represents the URL of the manifest/playlist of the media.</p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">type</span> </td> 
    <td colname="col2"> <p>One of the following string values that corresponds to the indicated file type: 
      <ul id="ul_7512E90B7B294EF9BFBA2D68DE678CBB"> 
       <li id="li_AA84434E84184A3D909552794B425ABD"><span class="codeph">MP4</span> - ISO base media file format (MP4) </li> 
       <li id="li_8A2F3752569344B59EE30303A8393488"><span class="codeph">HLS</span> - M3U8 </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"><span class="codeph">metadata</span> </td> 
    <td colname="col2"> <p>An instance of the <span class="codeph">Metadata</span> class, which might contain custom information about the content to be loaded. </p> <p>Examples of content are alternate or ad content to place inside the main content. If using advertising, set up <span class="codeph">AuditudeSettings</span> before using this constructor. For more information, see <a href="c_psdk_dhls_1.4_ad-insertion-metadata.xml" format="dita" scope="local">Ad Insertion Metadata</a>. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>   >[!IMPORTANT]
>   >
>   >supports playback for only specific types of content. If you attempt to load any other type of content, dispatches an error event.
>   >For MP4 video-on-demand (VOD) content,  does not support trick play, adaptive bit rate (ABR) streaming, ad insertion, closed captions, or DRM.
>   >
>   >
>   
>       
>       `codeph MediaResource`
>       
>       ```
>       // To do: Create metadata here
>       MyResource = new MediaResource(
>        "http://www.example.com/video/some-video.m3u8", 
>        "HLS",
>        MyMetadata)
>       ```
>       
>       
>       >[!TIP]
>       >
>       >At this point, you can use`codeph MediaResource` accessors (getters) to examine the resource's type, URL, and metadata.
>       
>   
>1. Load the media resource by using one of the following:
>* Your MediaPlayer instance.
>  For more information, see []().
>  
>  
>* A `codeph MediaPlayerItemLoader`
>  For more information, see []().
>  
>  
>   
>   
>   
