---
description: null
seo-description: null
seo-title: Replace time ranges with an Adobe Primetime ad decisioning ad
title: Replace time ranges with an Adobe Primetime ad decisioning ad
uuid: 23c5776b-97fa-4405-bc80-e0ad3c42f8e4
index: y
internal: n
snippet: y
---

# Replace time ranges with an Adobe Primetime ad decisioning ad{#replace-time-ranges-with-an-adobe-primetime-ad-decisioning-ad}

Remove `TimeRanges` between the `begin` and `end` in `localTime` from the timeline. Replace it with an AdBreak of `begin` to `begin+replaceDuration`. 

1. Replace ranges with Primetime ad decisioning ads.

   ```
   {   
       "properties": [],
       "stream": {
           "manifests": [ {
               "url": "http://. . ./cloudfront_vod_hls_tos_30fps.m3u8",
               "type": "hls"
           } ],
           "metadata": {
               "time-ranges": {
                   "type": "replace",
                   "time-range-list": [ {
                       "begin": 0,
                       "end": 15000,
                       "replace-duration": 15000
                   },
                   {
                       "begin": 69000,
                       "end": 99000,
                       "replacement-duration": 30000
                   },
                   {
                       "begin": 251000,
                       "end": 281000,
                       "replacement-duration": 30000
                   },
                   {
                       "begin": 514000,
                       "end": 544000,
                       "replacement-duration": 30000
                   } ]
   
               },
               "ad": {
                   "targeting": [ {
                       "value": "MulAdsAvail12346",
                       "key": "osmfKeyMulAdsAvail12346"
                   } ],
                   "domain": "sandbox2.auditude.com",
                   "mediaid": "psdk_000105",
                   "zoneid": "121781"
               }     
           }
       },   
       "title": "VOD - Replace TimeRange with Auditude Ads",
       "thumbnail": {
           "large": "http://example.com",
           "small": "http://example.com"
       },
       "type": "vod",
       "id": "vod_003"
   }
   
   ```

