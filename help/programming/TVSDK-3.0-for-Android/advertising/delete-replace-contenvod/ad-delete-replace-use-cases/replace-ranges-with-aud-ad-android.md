---
description: You can insert ads into VOD content.
seo-description: You can insert ads into VOD content.
seo-title: Replace time ranges with an ad
title: Replace time ranges with an ad
uuid: 53314c55-b1d6-4678-bd3e-85cff3c8ddad
index: y
internal: n
snippet: y
---

# Replace time ranges with an ad{#replace-time-ranges-with-an-ad}

You can insert ads into VOD content.

The `TimeRanges` between the `begin` and `end` in `localTime` are removed from the timeline. These ranges are replaced by an `AdBreak` of `begin` to `begin+replaceDuration`. If the `replacement-duration` does not exist as a parameter, the server makes the determination on the returned `Adbreak`.

>[!TIP]
>
>You should always provide a `replacement-duration` for custom ranges. If no ads are intended to replace this custom range, provide a `replacement-duration` of 0.

1. To replace the ranges with Primetime ad decisioningads:

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
                   "type": "replace",
                   "time-range-list": [
                       {
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
                       }
                   ]
               },
               "ad": {
                   "targeting": [
                       {
                           "value": "MulAdsAvail12346",
                           "key": "osmfKeyMulAdsAvail12346"
                       }
                   ],
               "domain": "sandbox2.auditude.com",
               "mediaid": "000105",
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

