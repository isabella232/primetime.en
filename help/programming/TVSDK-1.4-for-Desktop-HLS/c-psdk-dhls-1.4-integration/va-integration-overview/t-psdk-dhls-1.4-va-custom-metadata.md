---
description: You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.
seo-description: You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.
seo-title: Implement custom metadata support
title: Implement custom metadata support
uuid: ad23ac43-31f0-4aae-8abb-bfca36cd2eb1
index: y
internal: n
snippet: y
---

# Implement custom metadata support{#implement-custom-metadata-support}

You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.

Callback functions are invoked just before the tracking call is made, so your application can attach the metadata that is specific to an ad or chapter. 

1. Invoke callback functions for content, ads, and chapters.

   ```
   // Video Metadata Block 
   vaMetadata.videoMetadataBlock = function():Object { 
       return {"myvideoid":"1234", "mysdkversion":Version.version} 
   }; 
     
   // Ad Metadata Block invoked on every ad start 
   vaMetadata.adMetadataBlock = function(ad:Ad):Object { 
       return {"myadid":"ad-1234", "myad-sdkversion":Version.version} 
   }; 
     
   // Chapter Metadata Block invoked on every chapter start 
   vaMetadata.chapterMetadataBlock = function(chapter:VideoAnalyticsChapterData) { 
       return {"mychapterid":"chapter-1234", "mychapter-sdkversion":Version.version} 
   };
   ```

