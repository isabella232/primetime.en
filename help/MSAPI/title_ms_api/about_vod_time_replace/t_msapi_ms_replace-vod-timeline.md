---
description: Replace a VOD timeline by sending a new ad insertion request to the manifest server with an appropriately set pttimeline query parameter.
seo-description: Replace a VOD timeline by sending a new ad insertion request to the manifest server with an appropriately set pttimeline query parameter.
seo-title: Replace a VOD timeline
title: Replace a VOD timeline
uuid: 7d4fda48-5bd5-4896-9a33-438c6b1d9b7f
index: y
internal: n
snippet: y
translate: y
---

# Replace a VOD timeline

Replace a VOD timeline by sending a new ad insertion request to the manifest server with an appropriately set pttimeline query parameter.


1. Prepare an ad insertion request in the usual manner.
1. Set the `ptcueformat` query parameter to DPIScte35.
1. Set the `enableC3` query parameter to true or false as appropriate.
1. Create a `pttimeline` parameter using the VOD timeline format:
   1. Specify each content block (chapter) with `duration = 0` and `number_of_lots = 1`.
   1. Specify each ad block as usual, but set `lots = 0` to remove a break. Set `duration = 0` to use the ad break's duration (from the M3U8 file).
This example assumes the VOD content is in `Original.m3u8` with a timeline of `C,120,1;B,60,2,m;C,120,1;B,60,2,m;C,120,1;` 

The following manifest server request replaces the breaks in `Original.m3u8` with a 30-second pre-roll, followed by two breaks of duration two minutes each. 

```
http://manifest.auditude.com/auditude/variant/pubAsset/Original.m3u8?. . .&enableC3=false 
&pttimeline=B,30,2,p;C,0,1;B,120,4,m;C,0,1;B,120,4,m;C,0,1;
```
The following manifest server request removes the breaks in `Original.m3u8` and adds a 30-second pre-roll and a 30-second post-roll. 

```
http://manifest.auditude.com/auditude/variant/pubAsset/Original.m3u8?. . .&enableC3=false 
&pttimeline=B,30,2,p;C,0,1;B,0,0,m;C,0,1;B,0,0,m;C,0,1;B,30,2,t;
```
