---
description: You can implement Apple FairPlay Streaming, which is Apple's DRM solution, in your applications.
seo-description: You can implement Apple FairPlay Streaming, which is Apple's DRM solution, in your applications.
seo-title: Enable Apple FairPlay in TVSDK applications
title: Enable Apple FairPlay in TVSDK applications
---

# Enable Apple FairPlay in TVSDK applications

>1. Create your FairPlay Customer Resource Loader by implementing `codeph  PTAVAssetResourceLoaderDelegate`.
>   For more information, see [ Apple FairPlay in TVSDK applications ](c_psdk_ios_1.4_apple_fairplay_tvsdk.md#concept_79E840B2596A4E6B82E8FC3E40F7ADF9).
>   >[!NOTE] {type="attention"}
>   >
>   >Ensure that you follow the instructions in the*FairPlay Streaming Program Guide* ( *FairPlayStreaming_PG.pdf*), which is included in [ FairPlay Server SDK for Developing a FPS-Aware App ](https://developer.apple.com/services-account/download?path=/Developer_Tools/FairPlay_Streaming_SDK/FairPlay_Streaming_Server_SDK.zip)).
>   
>   The `codeph  resourceLoader:shouldWaitForLoadingOfRequestedResource` method is equivalent to what is in `codeph  AVAssetResourceLoaderDelegate`.
>   
>   >[!IMPORTANT] {importance="high"}
>   >
>   >In the ExpressPlay license server scenario, to play back content, change the URL scheme in your ExpressPlay FairPlay server license request URL from`codeph  skd://` to `codeph  http://` (or `codeph  https://`).
>   
>   
>1. Register the *FairPlay* Customer Resource Loader with `codeph  registerPTAVAssetResourceLoader`.
>   ```
>   PTFairPlayResourceLoader *resourceLoader = 
>    [[PTFairPlayResourceLoader new] autorelease]; 
>   [[PTDefaultMediaPlayerClientFactory defaultFactory] 
>    registerPTAVAssetResourceLoader:resourceLoader];
>   ```
>   
>   
>   
