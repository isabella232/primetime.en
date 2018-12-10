---
description: null
seo-description: null
seo-title: Implement chapter support
title: Implement chapter support
uuid: e2e00969-6967-4db1-8b6f-14645b4ff27f
index: y
internal: n
snippet: y
---

# Implement chapter support{#implement-chapter-support}

You can define and track *custom* chapters for video tracking in TVSDK-based applications.

Custom chapters are managed by the application, and are based on CMS data or on another way that the application uses to define chapters.

>[!CAUTION]
>
>Default chapters are not supported in the 3.0 Android TVSDK.

1. Define and track custom chapters.

   ```java
   // First, enable chapter tracking by setting   
   // enableChapterTracking to true: 
    
   vaMetadata.enableChapterTracking(true); 
   // For custom chapter definitions, provide  
   // an array list of chapters through the metadata. 
   // For example: 3 chapters of 60 second duration each 
    
   List<VideoAnalyticsChapterData> chapters =  
     new ArrayList<VideoAnalyticsChapterData>(); 
    
   Int chapterDuration = 60; 
   for (var i = 0; i < 3; i++) { 
       VideoAnalyticsChapterData chapterData =  
         new VideoAnalyticsChapterData(i * chapterDuration, (i + 1) * chapterDuration);  
       chapterData.setName("chapter_" + (i+1)); 
       chapters.add(chapterData); 
   } 
    
   vaMetadata.setChapters(chapters); 
   
   ```

