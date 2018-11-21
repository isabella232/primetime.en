---
seo-title: Example of a customized VOD asset
title: Example of a customized VOD asset
uuid: 4b7fea96-1a42-4225-9bbd-502984021077
index: y
internal: n
snippet: y
---

# Example of a customized VOD asset{#example-of-a-customized-vod-asset}

Here is an example of a customized VOD asset:

```
#EXTM3U
#EXT-X-VERSION:3
#EXT-X-TARGETDURATION:7
 
#EXT-X-ASSET:AID=10
 
#EXTINF:9.9766,
seg1.ts
 
#EXTINF:9.9766,
seg2.ts
 
#EXTINF:9.9766,
seg3.ts
 
#EXT-X-AD:DURATION=10
#EXTINF:9.9766,
seg4.ts
 
#EXTINF:9.9766,
seg5.ts
 
#EXT-X-ENDLIST
```

Your application could set up the following scenarios:

* A notification when `#EXT-X-ASSET` tags, or any other set of custom tag names to which you have subscribed, exist in the file. 
* Insert ads when an `#EXT-X-AD` tag, or any other custom tag name, is found in the stream.

