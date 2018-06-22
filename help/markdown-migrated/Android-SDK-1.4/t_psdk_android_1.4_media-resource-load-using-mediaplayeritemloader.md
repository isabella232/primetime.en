---
description: Another way to resolve a media resource is with MediaPlayerItemLoader. This is useful when you want to obtain information about a particular media stream without instantiating a MediaPlayer instance.
seo-description: Another way to resolve a media resource is with MediaPlayerItemLoader. This is useful when you want to obtain information about a particular media stream without instantiating a MediaPlayer instance.
seo-title: Load a media resource using MediaPlayerItemLoader
title: Load a media resource using MediaPlayerItemLoader
---

# Load a media resource using MediaPlayerItemLoader

Through the `codeph  MediaPlayerItemLoader` class, you can exchange a media resource for the corresponding `codeph  MediaPlayerItem` without attaching a view to a `codeph  MediaPlayer` instance, which would lead to the allocation of the video decoding hardware resources. The process of obtaining the `codeph  MediaPlayerItem` instance is asynchronous.

>1. Implement the `codeph  MediaPlayerItemLoader.LoaderListener` callback interface.
>   This interface defines two methods:
>* `codeph  LoaderListener.onError` callback function
>  uses this to inform your application that an error has occurred.  provides an error code as parameters and a description string that contains diagnostic information.
>  
>  
>* `codeph  LoaderListener.onError` callback function
>  uses this to inform your application that the requested information is available in the form of a `codeph  MediaPlayerItem` instance that is passed on as a parameter to the callback.
>  
>  
>   
>   
>1. Register this instance to  by passing it as a parameter to the constructor of the `codeph  MediaPlayerItemLoader`.
>   
>1. Call `codeph  MediaPlayerItemLoader.load`, passing an instance of a `codeph  MediaResource` object.
>   The URL of the `codeph  MediaResource` object must point to the stream for which you want to obtain information. For example:
>   ```java
>   // instantiate the listener interface 
>   MediaPlayerItemLoader.LoaderListener _itemLoaderListener = 
>    new MediaPlayerItemLoader.LoaderListener() { 
>    @Override 
>    public void onError(MediaErrorCode mediaErrorCode, String description) { 
>    // something went wrong - look at the error code and description 
>    } 
>    @Override 
>    public void onLoadComplete(MediaPlayerItem playerItem) { 
>    // information is available - look at the data in the "playerItem" object 
>    } 
>   } 
>    
>   // instantiate the MediaPlayerItemLoader object (pass the listener as parameter) 
>   MediaPlayerItemLoader itemLoader = new MediaPlayerItemLoader(_itemLoaderListener); 
>    
>   // create the MediaResource instance and set the URL to point to the actual media stream 
>   MediaResource mediaResource = 
>    MediaResource.createFromUrl("http://test.com/test_media.m3u8", null); 
>    
>   // load the media resource 
>   itemLoader.load(mediaResource); 
>   
>   ```
>   
>   
>   
>   
