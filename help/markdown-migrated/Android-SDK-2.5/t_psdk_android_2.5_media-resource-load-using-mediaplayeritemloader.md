---
description: Using MediaPlayerItemLoader helps you obtain information about a media stream without instantiating a MediaPlayer instance. This is especially useful in pre-buffering streams so that playback can begin without delay.
seo-description: Using MediaPlayerItemLoader helps you obtain information about a media stream without instantiating a MediaPlayer instance. This is especially useful in pre-buffering streams so that playback can begin without delay.
seo-title: Load a media resource using MediaPlayerItemLoader
title: Load a media resource using MediaPlayerItemLoader
---

# Load a media resource using MediaPlayerItemLoader

The `codeph  MediaPlayerItemLoader` class helps you exchange a media resource for the current `codeph  MediaPlayerItem` without attaching a view to a `codeph  MediaPlayer` instance, which would allocate video decoding hardware resources. Additional steps are necessary for DRM-protected content, but this manual does not describe them.

>[!IMPORTANT]
>
>does not support a single`codeph  QoSProvider` to work with both `codeph  itemLoader` and `codeph  MediaPlayer`. If your application uses Instant On, the application needs to maintain two `codeph  QoS` instances and manage both instances for the information. See []() for more information.
>1. Create an instance of `codeph  MediaPlayerItemLoader`.
>       
>       ```java
>       private MediaPlayerItemLoader createLoader() { 
>        MediaPlayerItemLoader itemLoader = 
>        new MediaPlayerItemLoader(this, new MediaPlayerItemLoader.LoaderListener() { 
>        public void onError(PSDKErrorCode mediaErrorCode, String description) { 
>        //Do something 
>        } 
>        
>        public void onLoadComplete(MediaPlayerItem playerItem) { 
>        loader.prepareBuffer(); 
>        } 
>        
>        public void onBufferingBegin() { 
>        //Do something 
>        } 
>        
>        public void onBufferPrepared() { 
>        mPlayer.reset(); 
>        } 
>        }); 
>        
>        itemLoader.setKeepRebufferingForLive(true); 
>        return itemLoader; 
>       } 
>       
>       ```
>       
>       >[!TIP]
>       >
>       >Create a separate instance of`codeph  MediaPlayerItemLoader` for each resource. Do not use one `codeph  MediaPlayerItemLoader` instance to load multiple resources.
>       
>   
>1. Implement the `codeph  ItemLoaderListener` class to receive notifications from the `codeph  MediaPlayerItemLoader` instance.
>       
>       ```java
>       private MediaPlayerItemLoader createLoader() { 
>        MediaPlayerItemLoader itemLoader = 
>        new MediaPlayerItemLoader(this, new MediaPlayerItemLoader.LoaderListener() { 
>        public void onError(PSDKErrorCode mediaErrorCode, String description) { 
>        //Do something 
>        } 
>        public void onLoadComplete(MediaPlayerItem playerItem) { 
>        loader.prepareBuffer(); 
>        } 
>        public void onBufferingBegin() { 
>        //Do something 
>        } 
>        public void onBufferPrepared() { 
>        mPlayer.reset(); 
>        } 
>        } ); 
>        
>        itemLoader.setKeepRebufferingForLive(true); 
>        return itemLoader; 
>       }
>       ```
>       
>       In the `codeph  onLoadComplete()` callback, do one of the following:
>    * Ensure that anything that might affect buffering, for example, selecting WebVTT or audio tracks, is complete and call `codeph  prepareBuffer()` to take advantage of instant on.
>    * Attach the item to the `codeph  MediaPlayer` instance by using `codeph  replaceCurrentItem()`.
>       If you call`codeph  prepareBuffer()`, you receive the BUFFER_PREPARED event in your `codeph  onBufferPrepared` handler when the preparation is finished.
>       
>       
>   
>1. Call `codeph  load` on the `codeph  MediaPlayerItemLoader` instance and pass the resource to be loaded, and optionally the content ID, and a `codeph  MediaPlayerItemConfig` instance.
>       
>       ```java
>       loader = createLoader(); 
>       MediaResource res = new MediaResource(mVideoUrl, MediaResource.Type.HLS, metadata); 
>       loader.load(res, 233, getConfig());
>       ```
>       
>   
>1. To buffer from a point other than the beginning of the stream, call `codeph  prepareBuffer()` with the position (in milliseconds) at which to start buffering.
>   
>1. Use the `codeph  replaceCurrentItem()` and `codeph  play()` methods of `codeph  MediaPlayer` to start playing from that point.
>   
>1. Wait for idle status and call `codeph  replaceCurrentItem`.
>   
>1. Play the item.
>* If the item is loaded but not buffered:
>    1. Wait for initialized status.
>    1. Call `codeph  prepareToPlay()`.
>    1. Wait for the PREPARED status.
>    1. Call `codeph  play()`.
>  
>* If the item is buffered:
>    1. Wait for the buffer prepared event.
>    1. Call `codeph  play()`.
>  
>   
>   
>   
