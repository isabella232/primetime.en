---
description: You can use Adobe's Offline packager to prepare content for any of the DRM solutions supported by Primetime Cloud DRM, powered by ExpressPlay.
seo-description: You can use Adobe's Offline packager to prepare content for any of the DRM solutions supported by Primetime Cloud DRM, powered by ExpressPlay.
seo-title: Primetime Packager / Cloud DRM / TVSDK
title: Primetime Packager / Cloud DRM / TVSDK
uuid: e54a0e4d-c8ea-46d4-b1b0-bed8a680f8f5
index: y
internal: n
snippet: y
---

# Primetime Packager / Cloud DRM / TVSDK{#primetime-packager-cloud-drm-tvsdk}

You can use Adobe's Offline packager to prepare content for any of the DRM solutions supported by Primetime Cloud DRM, powered by ExpressPlay.

 This set of instructions assumes you have already set up an ExpressPlay admin account: [Primetime DRM Cloud Quick-start](../../../multi-drm-workflows/quick-start/quick-overview.md). 
1. Choose the infrastructure to use for packaging your content. Primetime Packager supports both command-line and configuration-based packaging of content for use with the FairPlay, Widevine, and PlayReady DRMs. The following formats and encryption are currently supported in TVSDK (with more in the pipeline):

    * DASH (CENC) / PlayReady, Widevine - For HTML5 
    * HLS / FairPlay, Access - For iOS

1. Choose a Key Management System (KMS):

    * Use ExpressPlay's KMS ( [ExpressPlay Key Storage](https://www.expressplay.com/developer/key-storage/)); this system manages your content keys via ExpressPlay's RESTful API.

      or... 
    
    * Set up your own KMS. Create a database of content keys, selectable by Content-ID.

       In either case, the KMS manages a supply of content keys, with each key having an associated Content-ID.

1. Package your content. With Primetime Packager, you can package a piece of content for a specific DRM solution, or for multiple DRM solutions.

       The following sample commands show some examples of packaging content for different DRM solutions:

    * [Widevine with Primetime Packager](https://help.adobe.com/en_US/primetime/packagers/offline/index.html#Packagers-task-Protecting_content_using_Widevine_DRM_for_DASH) (generates MPD file):     
    
      ```    
      java -jar OfflinePackager.jar \ 
        -in_path [ 
<i>your_content.mp4</i>] \ 
        -out_type dash \ 
        -out_path [ 
<i>your_out_file_path</i>] \ 
        -drm \ 
        -drm_sys WIDEVINE \ 
        -key_file_path "creds/widevine_key.bin" \ 
        -widevine_key_id [ 
<i>some_keyID</i>] \ 
        -widevine_content_id [ 
<i>some_content-ID</i>] \ 
        -widevine_header provider:intertrust#content_id:2a
      ```

    * [FairPlay with Primetime Packager](https://help.adobe.com/en_US/primetime/packagers/offline/index.html#Packagers-task-Protecting_content_using_FairPlay_DRM) (Generates an M3U8 file):     
    
      ```    
      java -jar OfflinePackager.jar  
        -in_path [ 
<i>your_content.mp4</i>]  
        -out_type hls  
        -out_path [ 
<i>your_out_file_path</i>]  
        -drm  
        -drm_sys FAIRPLAY  
        -key_file_path "creds/fairplay_key.bin"  
        -key_url "user_provided_value"
      ```

       >[!NOTE]
       >
       >The `key_url` value is copied as is in the M3U8 file.

1. Create a "storefront server".

       The storefront server needs to handle the following operations:

    1. Customer selection of content. This implementation needs to include an endpoint for clients to request a content token for a specific content ID. 
    1. Customer entitlement 
    1. License token (ExpressPlay) requests from the client ( [ExpressPlay license token request / response reference](../../../multi-drm-workflows/license-token-req-resp-ref/license-req-resp-overview.md))

1. Create your client.

       The client should include a call to your storefront server. Adobe recommends that the client call the storefront after the user selects some content, and after the user is authenticated. Then, pass the token returned from ExpressPlay to your player to use for license requests. Introductions to implementing the DRM component of your players are here:

    * [Browser TVSDK for HTML5](https://help.adobe.com/en_US/primetime/psdk/browser_tvsdk/index.html#PSDKs-reference-DRM_interface_overview) 
    * [iOS](https://help.adobe.com/en_US/primetime/psdk/ios/index.html#PSDKs-task-Enable_Apple_FairPlay_in_TVSDK_applications)

1. With the license token in hand, the client can now derive the request URL from the token and make the license request to ExpressPlay, and then play the selected content for the user.
