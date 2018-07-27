---
description: You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.
seo-description: You can provide custom metadata on content, ads, and chapter tracking calls by using callback functions.
seo-title: Implement custom metadata support
title: Implement custom metadata support
uuid: d0e2451e-d3fc-473a-a596-da9e508fcef5
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
>   java>   // Video Metadata Block 
>   vaMetadata.setVideoMetadataBlock(new VideoAnalyticsMetadata.VideoMetadataBlock() { 
>       @Override 
>       public HashMap&lt;String, String&gt; call() { 
>           HashMap&lt;String, String&gt; result = new HashMap&lt;String, String&gt;(); 
>           result.put("myvideoid", "1234"); 
>           result.put("mysdkversion", Version.getVersion()); 
>     
>           return result; 
>       } 
>   }); 
>     
>   // Ad Metadata Block invoked on every ad start 
>   vaMetadata.setAdMetadataBlock(new VideoAnalyticsMetadata.AdMetadataBlock() { 
>       @Override 
>       public HashMap&lt;String, String&gt; call(Ad ad) { 
>           HashMap&lt;String, String&gt; result = new HashMap&lt;String, String&gt;(); 
>           result.put("myadid", "ad-1234"); 
>           result.put("myad-sdkversion", Version.getVersion()); 
>     
>           return result; 
>       } 
>   }); 
>     
>   // Chapter Metadata Block invoked on every chapter start 
>   vaMetadata.setChapterMetadataBlock(new VideoAnalyticsMetadata.ChapterMetadataBlock() { 
>       @Override 
>       public HashMap&lt;String, String&gt; call(VideoAnalyticsChapterData chapter) { 
>           HashMap&lt;String, String&gt; result = new HashMap&lt;String, String&gt;(); 
>           result.put("mychapterid", "chapter-1234"); 
>           result.put("mychapter-sdkversion", Version.getVersion()); 
>     
>           return result; 
>       } 
>   });
>   ```
>
