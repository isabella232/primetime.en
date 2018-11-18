---
description: null
seo-description: null
seo-title: Mark ranges
title: Mark ranges
uuid: 2d4156db-a1d6-46d4-9926-0ff30ea34c3f
index: y
internal: n
snippet: y
---

# Mark ranges{#mark-ranges}

Mark `TimeRanges` between the `begin` and `end` in `localTime` as an `AdBreak` from the timeline. Other Ad settings are ignored. 

1. Mark time ranges.

   ```
   {   
       "properties": [],
       "stream": {
           "manifests": [ {
               "url": "http://d398890tia84ty.cloudfront.net/e2e-vod/cloudfront_vod_hls_tos_30fps.m3u8",
               "type": "hls"
           } ],
           "metadata": {
               "time-ranges": {
                   "type": "mark",
                   "adjust-seek-position" : true,   
                   "time-range-list": [ {
                       "begin": 0,
                       "end": 15000
                   },
                   {
                       "begin": 69000,
                       "end": 99000
                   },
                   {
                       "begin": 251000,
                       "end": 281000
                   },
                   {
                       "begin": 514000,
                       "end": 544000
                   } ]
   
               }
           }           
       },   
       "title": "VOD - MARK TimeRanges and no ads",
       "thumbnail": {
           "large": "http://example.com",
           "small": "http://example.com"
       },
       "type": "vod",
       "id": "vod_004"
   }
   
   ```

