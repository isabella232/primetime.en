---
description: You can implement Apple FairPlay Streaming, which is Apple's DRM solution, in your TVSDK applications.
seo-description: You can implement Apple FairPlay Streaming, which is Apple's DRM solution, in your TVSDK applications.
seo-title: Enable Apple FairPlay in TVSDK applications
title: Enable Apple FairPlay in TVSDK applications
uuid: 779d8e56-019b-4b9b-b4e8-0bb86295f06e
index: y
internal: n
snippet: y
translate: y
---

# Enable Apple FairPlay in TVSDK applications

You can implement Apple FairPlay Streaming, which is Apple's DRM solution, in your TVSDK applications.


1. Create your FairPlay Customer Resource Loader by implementing `PTAVAssetResourceLoaderDelegate`.

   For more information, see [Apple FairPlay in TVSDK applications](../../../c_ios_titlepage/c_ios_drm-content-security/c_ios_apple_fairplay_tvsdk/c_ios_apple_fairplay_tvsdk.md#concept_79E840B2596A4E6B82E8FC3E40F7ADF9). 
   >[!NOTE] {type="attention"}
   >
   >Ensure that you follow the instructions in the*FairPlay Streaming Program Guide* ( *FairPlayStreaming_PG.pdf*), which is included in [FairPlay Server SDK for Developing a FPS-Aware App](https://developer.apple.com/services-account/download?path=/Developer_Tools/FairPlay_Streaming_SDK/FairPlay_Streaming_Server_SDK.zip)). 


   The `resourceLoader:shouldWaitForLoadingOfRequestedResource` method is equivalent to what is in `AVAssetResourceLoaderDelegate`. 

   >[!IMPORTANT] {importance="high"}
   >
   >In the ExpressPlay license server scenario, to play back content, change the URL scheme in your ExpressPlay FairPlay server license request URL from `skd://` to `http://` (or `https://`). 

1. Register the *FairPlay* Customer Resource Loader with `registerPTAVAssetResourceLoader`.

   ```
   PTFairPlayResourceLoader *resourceLoader =  
     [[PTFairPlayResourceLoader new] autorelease];  
   [[PTDefaultMediaPlayerClientFactory defaultFactory]  
     registerPTAVAssetResourceLoader:resourceLoader];
   ```

If you wrote your own FairPlay license server, or you are using a third-party FairPlay license server, consult your license server vendor to determine your license server URL, formatting, and any other requirements. 
