---
description: The MediaResource class represents the content to be loaded by the MediaPlayer instance.
seo-description: The MediaResource class represents the content to be loaded by the MediaPlayer instance.
seo-title: Create a media resource
title: Create a media resource
---

# Create a media resource

>1. Create a `codeph  MediaResource` by passing information about the media to the `codeph  MediaResource` constructor.
<table id="table_DD0D5D9129D54F73881399B9B4FF546A"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="2.99*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> Constructor Parameter </th> 
    <th colname="col2" class="entry"> Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> <p>url </p> </td> 
    <td colname="col2"> <p>A string that represents the URL of the manifest/playlist of the media. </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>type </p> </td> 
    <td colname="col2"> <p>One of the following members of the <span class="codeph"> MediaResource.Type </span> enumeration that corresponds to the indicated file type: 
      <ul id="ul_72636C41CA7E4538A3BE11A79E0282FC"> 
       <li id="li_070960200DEB40E992C58FCB8909AEA3"> <span class="codeph"> HLS </span> - M3U8 </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> <p>metadata </p> </td> 
    <td colname="col2"> <p>An instance of the <span class="codeph"> Metadata </span> class, which might contain custom information about the content to be loaded. </p> <p>Examples of content are alternate or ad content to place inside the main content. If using advertising, set up <span class="codeph"> AuditudeSettings </span>. For more information, see <a href="c_psdk_android_1.4_ad-insertion-metadata.xml" format="dita" scope="local"> Ad Insertion Metadata </a>. </p> </td> 
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
>       `codeph  MediaResource`
>       
>       ```java
>       try { 
>        // create a MediaResource instance pointing to some HLS content 
>        Metadata metadata = //TODO: create metadata 
>        MediaResource mediaResource = MediaResource.createFromUrl( 
>        "http://www.example.com/video/some-video.m3u8", 
>        MediaResource.Type.HLS, 
>        metadata); 
>       } catch(IllegalArgumentException ex) { 
>        // this exception is thrown if the URL does not point 
>        // to a valid url. 
>       } 
>       
>       ```
>       
>       
>       >[!TIP]
>       >
>       >At this point, you can use`codeph  MediaResource` accessors (getters) to examine the resource's type, URL, and metadata.
>       
>   
>1. Load the media resource by using the following:
>* Your MediaPlayer instance.
>  For more information, see []().
>  
>  
>* A `codeph  MediaPlayerItemLoader`
>  For more information, see []().
>  
>  
>   
>   >[!IMPORTANT]
>   >
>   >Do not load the media resource on a background thread. Most operations need to be run on the main thread, and running them on a background thread can cause the operation to throw an error and exit.
>   
>   
>   
