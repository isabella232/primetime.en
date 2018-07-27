---
description: null
seo-description: null
seo-title: Special Use Cases
title: Special Use Cases
uuid: 3d1e74d6-1d2b-4d9d-b1f6-d912c0a8aa3b
index: n
internal: n
snippet: y
translate: y
---

# Special Use Cases

 <!-- PH element: phrases/primetime-sdk-name --> favors custom range settings over standard ad settings. For example, if MARK ranges are defined, the ad's insertion settings are ignored. If REPLACE ranges are defined, <!-- PH element: phrases/primetime-sdk-name --> automatically uses the `CustomRanges` signaling mode.

>1. `ReplaceRange` without replacement duration
>   If the replacement duration is missing, the actual replacement duration is determined by the server. The number of ads placed in this `AdBreak` is also determined by the server.>
>   ```
>   {
>       "properties": [],
>       "stream": {
>           "manifests": [ {
>               "url": "http://. . ./vanilla/index.m3u8",
>               "type": "hls"
>           } ],
>           "metadata": {
>               "signaling-mode": "custom time ranges",
>               "time-ranges": {
>                   "type": "replace",
>                   "adjust-seek-position": true,
>                   "time-range-list": [{
>                   "begin": 0,
>                   "end": 30000
>               }, {
>                   "begin": 60000,
>                   "end": 75000
>               }, {
>                   "begin": 255000,
>                   "end": 300000
>               } ]
>               },
>               "ad": {             
>                   "domain": "sandbox2.auditude.com",
>                   "mediaid": "psdk_000105",
>                   "zoneid": "121781"
>               }     
>           }
>       },
>       "title": "Verify 30Sec Pre-Roll, 15 Sec Mid roll Ad and 
>       45 second Post-Roll can be replaced in one shot.",
>       "thumbnail": {
>           "large": "http://example.com",
>           "small": "http://example.com"
>       },
>       "type": "vod",
>       "id": "vod_001"
>   }
>   
>   ```
>
>1. MARK and DELETE ranges with replacement duration
>   The extra replacement duration is ignored.>
