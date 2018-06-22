---
description: 
seo-description: 
seo-title: Implement chapter support
title: Implement chapter support
---

# Implement chapter support

You can define and track chapters for video tracking in a -based application in the following ways:
* Default chapters, which are managed internally by .
  A chapter is defined as the time between each ad break. For example, the time between a pre-roll ad break and the first mid-roll is defined as the first chapter.
  
  
* Custom chapters, which are managed by the application and are based on CMS data or another way that the application uses to define chapters.

>1. Define and track default or custom chapters.
>   ```java
>   // First, enable chapter tracking by setting 
>   // the Boolean 'enableChapterTracking' to true: 
>    
>   vaMetadata.enableChapterTracking(true); 
>   // For custom chapter definitions, provide an array list of chapters 
>   // through the metadata. 
>   // For example: 3 chapters of 60 second duration each 
>    
>   List&lt;VideoAnalyticsChapterData&gt; chapters = new ArrayList&lt;VideoAnalyticsChapterData&gt;(); 
>    
>   Int chapterDuration = 60; 
>   for (var i = 0; i &lt; 3; i++) { 
>    VideoAnalyticsChapterData chapterData = 
>    new VideoAnalyticsChapterData(i * chapterDuration, (i + 1) * chapterDuration); 
>    chapterData.setName("chapter_" + (i+1)); 
>    chapters.add(chapterData); 
>   } 
>    
>   vaMetadata.setChapters(chapters); 
>   // For default chapters, the application must not set 
>   // custom chapters on the tracking metadata 
>   // and simply enable chapters to be tracked by setting 
>   // the boolean value as defined above.
>   ```
>   
>   
>   
