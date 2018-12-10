---
description: You can designate time intervals in VOD content as ad breaks.
seo-description: You can designate time intervals in VOD content as ad breaks.
seo-title: Mark ranges
title: Mark ranges
uuid: 77589eb9-5981-42c3-98c6-7cf962db50bd
index: y
internal: n
snippet: y
---

# Mark ranges{#mark-ranges}

You can designate time intervals in VOD content as ad breaks.

The `TimeRanges` between the `begin` and `end` in `localTime` will be marked as an `AdBreak` in the timeline. Other ad settings are ignored.

>[!TIP]
>
>If you want to only mark certain ranges in the content as ads, with no dynamic ad insertion, create a `CustomRangeMetadata` instance, and specify the type as a `MARK` operation with the defined custom ranges.

1. Tp mark the ranges:

   ```
   {   
       "properties": [],
       "stream": {
           "manifests": [
               {
                   "url": "http://d398890tia84ty.cloudfront.net/e2e-vod/cloudfronvod_hls_tos_30fps.m3u8",
                   "type": "hls"
               }
           ],
            
       "metadata": {
           "time-ranges": {
                   "type": "mark",
               "adjust-seek-position" : true,   
                   "time-range-list": [
                     {
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
                       }
                    ]
    
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

