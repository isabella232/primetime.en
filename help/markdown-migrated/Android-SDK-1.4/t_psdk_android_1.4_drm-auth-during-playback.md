---
description: When the DRM metadata for a video is included in the media stream, perform authentication during playback.
seo-description: When the DRM metadata for a video is included in the media stream, perform authentication during playback.
seo-title: DRM authentication during playback
title: DRM authentication during playback
---

# DRM authentication during playback

Consider the license rotation feature, where an asset is encrypted with multiple DRM licenses. Each time that new DRM metadata is discovered, use `codeph  DRMHelper` methods to check whether the DRM metadata requires DRM authentication.

>[!NOTE]
>
>This tutorial does not handle domain bound licenses. Ideally, before starting playback, check whether you are dealing with a domain bound license. If yes, perform domain authentication (if needed) and join the domain.
>
>
>1. When new DRM Metadata is discovered in an asset, an event is dispatched at the application layer.
>   ```java
>   mediaPlayer.addEventListener(MediaPlayerEvent.DRM_METADATA, 
>    drmMetadataInfoEventListener); 
>    
>   DRMMetadataInfoEventListener drmMetadataInfoEventListener = 
>    new DRMMetadataInfoEventListener() { 
>    @Override 
>    public void onDRMMetadataInfo(DRMMetadataInfoEvent drmMetadataInfoEvent) { 
>    } 
>   };
>   ```
>   
>   
>1. Use the `codeph  DRMMetadata` to check whether authentication is needed. If not, do nothing; playback continues uninterrupted.
>   
>1. Otherwise, perform DRM authentication. Since this operation is asynchronous and is handled in a different thread, it has no impact on the user interface nor on video playback.
>   
>1. If authentication fails, the user cannot continue viewing the video, and playback ceases. Otherwise, playback will continue uninterruptedly.
>   
>   
