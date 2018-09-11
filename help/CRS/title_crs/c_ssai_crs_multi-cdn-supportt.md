---
description: Multi CDN allows for the setting of one or more CDN locations to serve transcoded ads.
seo-description: Multi CDN allows for the setting of one or more CDN locations to serve transcoded ads.
seo-title: Multi CDN support
title: Multi CDN support
uuid: 327826fa-6076-457a-9c8b-fa96473ce264
index: y
internal: n
snippet: y
translate: y
---

# Multi CDN support

Multi CDN allows for the setting of one or more CDN locations to serve transcoded ads.

By default, all transcoded assets are hosted on the Adobe-owned Akamai CDN. However, you can choose zero or more additional CDN locations of your own where CRS will host the transcoded asset. So in this case, your transcoded assets and content can be served from the same CDN. 

When the manifest server makes a look-up for transcoded requests, it uses a bootstrap URL that contains a number of query parameters. If you have set up a multi-CDN environment, the bootstrap URL will also need to contain the `ptcdn` parameter.The manifest server uses this parameter to identify the CDN server from which to get the transcoded version of the ad. 

Multi CDN support is also available for the following Primetime solutions: 
1. TVSDK for Android1. TVSDK for Desktop HLS1. TVSDK for iOS



## Enable CDN support {#section_1BA344F2300B49F291865A7461EDFEAE}

By default, CRS is disabled for all customers 

Contact your Adobe technical account manager to configure your CRS account to use other CDNs to host the transcoded ad assets.You will be required to provide the following information that is needed by CRS to upload the transcoded ad assets to the CDN 

1. CDN URL1. Authentication details1. Output URL format

Also, your Adobe techincal account manager will provide you a nickname for this CDN.You need to pass this as the value of the ptcdn parameter in the Bootstrap URL. 

You can have multiple CDNs configured on CRS end via Adobe Support. However, the CDN that is used to pick ad assets to be stitched via the manifest server would need to be the one that is passed as the value of the ptcdn parameter in the Bootstrap URL. 
