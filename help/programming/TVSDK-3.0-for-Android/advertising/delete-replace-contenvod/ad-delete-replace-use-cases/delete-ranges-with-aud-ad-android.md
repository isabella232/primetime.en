---
description: You can remove TimeRanges between begin and end in localTime from the timeline.
seo-description: You can remove TimeRanges between begin and end in localTime from the timeline.
seo-title: Delete ranges
title: Delete ranges
uuid: cee8cbaf-de96-4d8b-b20a-bd4752fb6bb3
index: y
internal: n
snippet: y
---

# Delete ranges{#delete-ranges}

You can remove TimeRanges between begin and end in localTime from the timeline.

>[!TIP]
>
>To only remove certain ranges from the content, create a `CustomRangeMetadata` instance and specify the type as a `DELETE` operation with the defined custom ranges.

The ad map must be used as defined by the ad server. 

1. To delete ranges with an Adobe Primetime ad decisioning ad:

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
                   "type": "delete",
                   "time-range-list": [
                       {
                           "begin": 0,
                           "end": 20000
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
       "title": "VOD - DELETE TimeRange with xm-replace_text Phrase Ads",
       "thumbnail": {
           "large": "http://example.com",
           "small": "http://example.com"
       },
       "type": "vod",
       "id": "vod_003"
   },
   
   ```

