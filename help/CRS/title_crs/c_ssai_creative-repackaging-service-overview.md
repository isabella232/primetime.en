---
description: The creative repackaging service (CRS) ensures that a non-HLS ad creative can play back properly in HLS streams. The manifest server calls on CRS when it encounters a non-HLS ad.
keywords: enable crs;enable creative repackaging service
seo-description: The creative repackaging service (CRS) ensures that a non-HLS ad creative can play back properly in HLS streams. The manifest server calls on CRS when it encounters a non-HLS ad.
seo-title: Overview of CRS
title: Overview of CRS
uuid: 721fb8d8-f25d-4f60-b4b5-63bed3752641
index: y
internal: n
snippet: y
translate: y
---

# Overview of CRS

The creative repackaging service (CRS) ensures that a non-HLS ad creative can play back properly in HLS streams. The manifest server calls on CRS when it encounters a non-HLS ad.


>[!NOTE]
>
>By default, CRS is disabled. To enable CRS for your account, contact your Adobe technical account manager.For information on enabling CRS within TVSDK apps, see the *Enable CRS in TVSDK applications* topic in the Programmer's Guide for your platform. For example, for Android 2.5, see [Enable CRS in TVSDK applications](http://help.adobe.com/en_US/primetime/psdk/android/2.5/index.html#Enable_CRS_in_TVSDK_applications) 

CRS prepares HTTP Live Streaming (HLS) ad creatives for the content stream and injects ID3 packets for client-side ad tracking. It transcodes MP4, FLV, and WebM files received from third-party ad servers, ad networks, and agency servers into HLS format. 

When Adobe Primetime ad insertion encounters a non-HLS ad creative, it sends it to CRS for repackaging, which typically takes no longer than three minutes. CRS sends the transcoded ad creative to the CDN server for future use. This is called *`just-in-time (JIT) repackaging`*. You can also transcode ad creatives before they're needed using the  crs_async_repackage . This is called *`asynchronous repackaging`*. 

Your Adobe technical account manager can also change some CRS default behaviors if another behavior is better suited to your application. These are: 
* Priority of ad creative formats. The `MediaFiles` section of a VAST/VMAP response can contain creatives with different `MediaFile` types. By default the manifest server selects one according to a fixed set of priorities ( `application/x-mpegURL`, `application/vnd.apple.mpegURL`, `video/mp4`, `video/x-flv,video/webm`). Adobe can change the priorities for your account. 

* Ad target duration. The manifest server detects the target ad duration from the content playlist and sends it to CRS. Adobe can change this behavior so that CRS always uses a fixed duration that you specify for your account. 




