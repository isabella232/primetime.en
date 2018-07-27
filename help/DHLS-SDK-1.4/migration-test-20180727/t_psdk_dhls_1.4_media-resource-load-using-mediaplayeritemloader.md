---
description: Another way to resolve a media resource is with MediaPlayerItemLoader. This is useful when you want to obtain information about a particular media stream without instantiating a MediaPlayer instance.
seo-description: Another way to resolve a media resource is with MediaPlayerItemLoader. This is useful when you want to obtain information about a particular media stream without instantiating a MediaPlayer instance.
seo-title: Load a media resource using MediaPlayerItemLoader
title: Load a media resource using MediaPlayerItemLoader
uuid: 1f586b7b-cba6-4bf3-b243-af8da39f0d1d
index: n
internal: n
snippet: y
translate: y
---

# Load a media resource using MediaPlayerItemLoader

Through the ` MediaPlayerItemLoader` class, you can exchange a media resource for the corresponding ` MediaPlayerItem` without attaching a view to a ` MediaPlayer` instance, which would lead to the allocation of the video decoding hardware resources. The process of obtaining the ` MediaPlayerItem` instance is asynchronous. 

>1. Implement event listeners for these ` MediaPlayerItemLoader` events:
>    
>    * ` MediaPlayerItemLoaderEvent.ERROR` event  <!-- PH element: phrases/primetime-sdk-name --> uses this to inform your application that an error has occurred. <!-- PH element: phrases/primetime-sdk-name --> provides an error property that contains diagnostic information.

>    
>1. Register this instance to the ` MediaPlayerItemLoader`.
>1. Call ` DefaultMediaPlayerItemLoader.load`, passing an instance of a ` MediaResource` object.
>   The URL of the ` MediaResource` object must point to the stream for which you want to obtain information. For example: >
>   ```
>   private function onLoadError(event:MediaPlayerItemLoaderEvent):void { 
>       // something went wrong - look at the error code and description 
>       // contained within the event.error 
>   } 
>   private function onLoadCompleted(event:MediaPlayerItemLoaderEvent):void { 
>       // information is available - look at the data in the "event.item" object 
>   } 
>   // instantiate the MediaPlayerItemLoader object and register event listeners 
>   var itemLoader:MediaPlayerItemLoader = new DefaultMediaPlayerItemLoader(); 
>   itemLoader.addEventListener(MediaPlayerItemLoaderEvent.ERROR, onLoadError); 
>   itemLoader.addEventListener(MediaPlayerItemLoaderEvent.COMPLETED, onLoadCompleted); 
>   // create the MediaResource instance and set the URL to point to the actual media stream 
>   var mediaResource:MediaResource = 
>     MediaResource.createFromURL("http://example.com/media/test_media.m3u8", null); 
>   // load the media resource 
>   itemLoader.load(mediaResource); 
>   
>   ```

>
