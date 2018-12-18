---
description: You can insert ads into VOD content.
seo-description: You can insert ads into VOD content.
seo-title: Replace time ranges with an ad
title: Replace time ranges with an ad
uuid: 50cdcc06-7df5-414b-95d4-c684bc68dce3
index: y
internal: n
snippet: y
---

# Replace time ranges with an ad{#replace-time-ranges-with-an-ad}

You can insert ads into VOD content.

In this case, `TimeRanges` between the `begin` and `end` in `localTime` are removed from the timeline. They are replaced by an `AdBreak` of `begin` to `begin+replaceDuration`. If the replacement-duration does not exist as a parameter, the server makes the determination on the returned Adbreak.

>[!NOTE]
>
>You should always provide a specific replacement-duration for custom ranges. If no ads are intended to replace this custom range, provide a replacement-duration of 0.

1. Replace ranges with Primetime ad decisioning ads.

   ```
   {   
       "properties": [],
       "stream": {
           "manifests": [ {
               "url": 
                 "http://d398890tia84ty.cloudfront.net/e2e-vod/cloudfront_vod_hls_tos_30fps.m3u8",
               "type": "hls"
           } ],
                    
           "metadata": {
               "time-ranges": {
                   "type": "replace",
                   "time-range-list": [ {
                       "begin": 0,
                       "end": 15000,
                       "replacement-duration": 15000 
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

