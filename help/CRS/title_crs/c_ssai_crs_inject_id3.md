---
description: CRS can inject ID3 timed metadata into HLS format ad creatives to facilitate client-side ad tracking.
seo-description: CRS can inject ID3 timed metadata into HLS format ad creatives to facilitate client-side ad tracking.
seo-title: Using CRS to Inject ID3 Timed Metadata Tags
title: Using CRS to Inject ID3 Timed Metadata Tags
uuid: a777211d-501e-4973-91f4-9fab04a43544
index: y
internal: n
snippet: y
translate: y
---

# Using CRS to Inject ID3 Timed Metadata Tags

CRS can inject ID3 timed metadata into HLS format ad creatives to facilitate client-side ad tracking.

The client player reads the ID3 metadata to enable frame-accurate ad tracking. 
>[!NOTE]
>
>ID3 timed metadata injection works only on Safari on iOS.


**Workflow for CRS for ID3 Injection** 

The workflow for ID3 injection is the same as in  crs_jit_repackage . If the manifest server receives the `ptplayer=ios-mobileweb` parameter, it tells CRS to inject ID3 packets into the transcoded ad creative before uploading it to the CDN server. 

>[!NOTE]
>
>In a multi-CDN setup, the manifest server uses the `ptcdn` parameter in the bootstrap URL to identify the CDN server to upload the ad creative. 
