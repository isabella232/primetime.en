---
description: null
seo-description: null
seo-title: Implement chapter support
title: Implement chapter support
uuid: 893d6e67-0ab9-4850-aae5-c8ac4112b4fc
index: n
internal: n
snippet: y
translate: y
---

# Implement chapter support

You can define and track *custom* chapters for video tracking in  <!-- PH element: phrases/primetime-sdk-name --> -based applications.
Custom chapters are managed by the application, and are based on CMS data or on another way that the application uses to define chapters.

>[!CAUTION]
>
>Default chapters are not supported in the 2.5 Android <!-- PH element: phrases/primetime-sdk-name --> .


>1. Define and track custom chapters.
>
>   ```
>   java>   // First, enable chapter tracking by setting   
>   // enableChapterTracking to true: 
>    
>   vaMetadata.enableChapterTracking(true); 
>   // For custom chapter definitions, provide  
>   // an array list of chapters through the metadata. 
>   // For example: 3 chapters of 60 second duration each 
>    
>   List&lt;VideoAnalyticsChapterData&gt; chapters =  
>     new ArrayList&lt;VideoAnalyticsChapterData&gt;(); 
>    
>   Int chapterDuration = 60; 
>   for (var i = 0; i &lt; 3; i++) { 
>       VideoAnalyticsChapterData chapterData =  
>         new VideoAnalyticsChapterData(i * chapterDuration, (i + 1) * chapterDuration);  
>       chapterData.setName("chapter_" + (i+1)); 
>       chapters.add(chapterData); 
>   } 
>    
>   vaMetadata.setChapters(chapters); 
>   
>   ```
>
