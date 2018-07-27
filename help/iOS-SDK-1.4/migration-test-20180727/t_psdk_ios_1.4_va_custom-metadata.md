---
description: You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.
seo-description: You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.
seo-title: Implement custom metadata support
title: Implement custom metadata support
uuid: 125b6af6-4179-4fe3-a9dd-b02215b1c71e
index: n
internal: n
snippet: y
translate: y
---

# Implement custom metadata support

Callback functions are invoked just before the tracking call is made, so your application can attach the metadata that is specific to an ad or chapter.

>1. Invoke callback functions for content, ads, and chapters.
>
>   ```
>   // Video Metadata Block 
>       vaTrackingMetadata.videoMetadataBlock = ^NSDictionary *() 
>       { 
>           return @{ 
>                    @"myvideoid": @"1234", 
>                    @"mysdkversion": [PTSDK apiVersion] 
>                    }; 
>       }; 
>         
>   // Ad Metadata Block invoked on every ad start 
>       vaTrackingMetadata.adMetadataBlock = ^NSDictionary *(PTAd *ad) 
>       { 
>           return @{ 
>                    @"myadid": @"ad-1234", 
>                    @"myad-sdkversion": [PTSDK apiVersion] 
>                    }; 
>       }; 
>         
>   // Chapter Metadata Block invoked on every chapter start 
>       vaTrackingMetadata.chapterMetadataBlock = ^NSDictionary *(PTVideoAnalyticsChapterData *chapter) 
>       { 
>           return @{ 
>                    @"mychapterid": @"chapter-1234", 
>                    @"mychapter-sdkversion": [PTSDK apiVersion] 
>                    }; 
>       };
>   ```
>
