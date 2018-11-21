---
description: You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.
seo-description: You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.
seo-title: Implement custom metadata support
title: Implement custom metadata support
uuid: 0b07ad81-166f-432d-83bf-42cf5ed896fc
index: y
internal: n
snippet: y
---

# Implement custom metadata support{#implement-custom-metadata-support}

You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.

Callback functions are invoked just before the tracking call is made, so your application can attach the metadata that is specific to an ad or chapter. 

1. Invoke callback functions for content, ads, and chapters.

   ```js
   vaObj.videoMetadataBlock = function() { 
       return { 
           "name" : "my-video", 
           "genre" : "comedy" 
       }; 
   } 
     
   vaObj.adMetadataBlock = function(ad) { 
       return { 
           "name" : "my-ad", 
           "category" : "automotive" 
       }; 
   } 
     
   vaObj.chapterMetadataBlock = function(chapter) { 
       return { 
           "name" : "my-chapter", 
           "type" : "quartile" 
       }; 
   }
   ```

