---
description: When the DRM metadata for a video is included in the media stream, you can perform authentication during playback.
seo-description: When the DRM metadata for a video is included in the media stream, you can perform authentication during playback.
seo-title: DRM authentication during playback
title: DRM authentication during playback
uuid: 0b355f4a-c540-4a34-9b8a-4bcb2df3e2f2
index: n
internal: n
snippet: y
translate: y
---

# DRM authentication during playback

With license rotation, an asset is encrypted with multiple DRM licenses. Each time that new DRM metadata is discovered, the ` DRMHelper` methods are used to check whether the DRM metadata requires DRM authentication. 

>[!TIP]
>
>Before starting playback, determine whether you are dealing with a domain bound license and whether domain authentication is required. If yes, complete the domain authentication and join the domain.


>1. When new DRM Metadata is discovered in an asset, an event is dispatched at the application layer.
>
>   ```
>   java>   mediaPlayer.addEventListener(MediaPlayerEvent.DRM_METADATA,  
>                                drmMetadataInfoEventListener); 
>    
>   DRMMetadataInfoEventListener drmMetadataInfoEventListener =  
>     new DRMMetadataInfoEventListener() { 
>       @Override 
>       public void onDRMMetadataInfo(DRMMetadataInfoEvent drmMetadataInfoEvent) { 
>           ... 
>       } 
>   };
>   ```
>
>1. Use the ` DRMMetadata` to check whether authentication is needed.
>    
>    * If authentication is not required, you do not need to do anything, and playback continues uninterrupted.
>    * If authentication is required, complete DRM authentication. Since this operation is asynchronous and is handled in a different thread, it has no impact on the user interface nor on video playback.

>    
>1. If authentication fails, the user cannot continue viewing the video, and playback stops.
