---
description: Another way to resolve a media resource is with MediaPlayerItemLoader. This is useful when you want to obtain information about a particular media stream without instantiating a MediaPlayer instance.
seo-description: Another way to resolve a media resource is with MediaPlayerItemLoader. This is useful when you want to obtain information about a particular media stream without instantiating a MediaPlayer instance.
seo-title: Load a media resource using MediaPlayerItemLoader
title: Load a media resource using MediaPlayerItemLoader
uuid: dde8d6a2-3e40-4392-8dca-1bcbb25f5086
index: n
internal: n
snippet: y
translate: y
---

# Load a media resource using MediaPlayerItemLoader

Through the ` MediaPlayerItemLoader` class, you can exchange a media resource for the corresponding ` MediaPlayerItem` without attaching a view to a ` MediaPlayer` instance, which would lead to the allocation of the video decoding hardware resources. The process of obtaining the ` MediaPlayerItem` instance is asynchronous. 

>1. Implement the ` MediaPlayerItemLoader.LoaderListener` callback interface.
>       This interface defines two methods:>    
>    * ` LoaderListener.onError` callback function  <!-- PH element: phrases/primetime-sdk-name --> uses this to inform your application that an error has occurred. <!-- PH element: phrases/primetime-sdk-name --> provides an error code as parameters and a description string that contains diagnostic information.

>    * ` LoaderListener.onError` callback function  <!-- PH element: phrases/primetime-sdk-name --> uses this to inform your application that the requested information is available in the form of a ` MediaPlayerItem` instance that is passed on as a parameter to the callback. 

>    
>1. Register this instance to  <!-- PH element: phrases/primetime-sdk-name --> by passing it as a parameter to the constructor of the ` MediaPlayerItemLoader`.
>1. Call ` MediaPlayerItemLoader.load`, passing an instance of a ` MediaResource` object.
>   The URL of the ` MediaResource` object must point to the stream for which you want to obtain information. For example: >
>   ```
>   java>   // instantiate the listener interface 
>   MediaPlayerItemLoader.LoaderListener _itemLoaderListener = 
>     new MediaPlayerItemLoader.LoaderListener() { 
>       @Override 
>       public void onError(MediaErrorCode mediaErrorCode, String description) { 
>           // something went wrong - look at the error code and description 
>       } 
>       @Override 
>           public void onLoadComplete(MediaPlayerItem playerItem) { 
>           // information is available - look at the data in the "playerItem" object 
>       } 
>   } 
>    
>   // instantiate the MediaPlayerItemLoader object (pass the listener as parameter) 
>   MediaPlayerItemLoader itemLoader = new MediaPlayerItemLoader(_itemLoaderListener); 
>    
>   // create the MediaResource instance and set the URL to point to the actual media stream 
>   MediaResource mediaResource =  
>     MediaResource.createFromUrl("http://test.com/test_media.m3u8", null); 
>    
>   // load the media resource 
>   itemLoader.load(mediaResource); 
>   
>   ```

>
