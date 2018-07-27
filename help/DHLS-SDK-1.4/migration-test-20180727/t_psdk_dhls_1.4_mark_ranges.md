---
description: null
seo-description: null
seo-title: Mark ranges
title: Mark ranges
uuid: 6261d4af-e555-4210-a484-c731bf32f157
index: n
internal: n
snippet: y
translate: y
---

# Mark ranges

Mark `TimeRanges` between the `begin` and `end` in `localTime` as an `AdBreak` from the timeline. Other Ad settings are ignored. 

>1. Mark time ranges.
>
>   ```
>   {   
>       "properties": [],
>       "stream": {
>           "manifests": [ {
>               "url": "http://d398890tia84ty.cloudfront.net/e2e-vod/cloudfront_vod_hls_tos_30fps.m3u8",
>               "type": "hls"
>           } ],
>           "metadata": {
>               "time-ranges": {
>                   "type": "mark",
>                   "adjust-seek-position" : true,   
>                   "time-range-list": [ {
>                       "begin": 0,
>                       "end": 15000
>                   },
>                   {
>                       "begin": 69000,
>                       "end": 99000
>                   },
>                   {
>                       "begin": 251000,
>                       "end": 281000
>                   },
>                   {
>                       "begin": 514000,
>                       "end": 544000
>                   } ]
>   
>               }
>           }           
>       },   
>       "title": "VOD - MARK TimeRanges and no ads",
>       "thumbnail": {
>           "large": "http://example.com",
>           "small": "http://example.com"
>       },
>       "type": "vod",
>       "id": "vod_004"
>   }
>   
>   ```
>
