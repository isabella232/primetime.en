---
description: Ad insertion resolves ads for video-on-demand (VOD) , for live streaming, and for linear streaming with ad tracking and ad playback. makes the required requests to the ad server, receives information about ads for the specified content, and places the ads in the content in phases.
seo-description: Ad insertion resolves ads for video-on-demand (VOD) , for live streaming, and for linear streaming with ad tracking and ad playback. makes the required requests to the ad server, receives information about ads for the specified content, and places the ads in the content in phases.
seo-title: Inserting ads
title: Inserting ads
uuid: 98674f92-e35b-4539-a270-e7ec7a6f3bd5
index: n
internal: n
snippet: y
translate: y
---

# Inserting ads

An * ` ad break` * contains one or more ads that play in sequence.  <!-- PH element: phrases/primetime-sdk-name --> inserts ads in the main content as members of one or more ad breaks.
To disable pre-roll, change the default opportunity generators to not make the pre-roll call. The default opportunity generators is: 
```
@inheritDoc 
*/ 
override protected function doRetrieveGenerators(item:MediaPlayerItem):Vector.&lt;OpportunityGenerator&gt; { 
var result:Vector.&lt;OpportunityGenerator&gt; = new Vector.&lt;OpportunityGenerator&gt;(); 
result.push(new AdSignalingModeOpportunityGenerator()); 
result.push(new SpliceOutOpportunityGenerator()); 
return result; 
}
```

To disable the pre-roll on live streams, change the above to include only the SpliceOutOpportunityGenerator: 
```
@inheritDoc 
*/ 
override protected function doRetrieveGenerators(item:MediaPlayerItem):Vector.&lt;OpportunityGenerator&gt; { 
var result:Vector.&lt;OpportunityGenerator&gt; = new Vector.&lt;OpportunityGenerator&gt;(); 
if (preroll_enabled == true) { result.push(new AdSignalingModeOpportunityGenerator()); } 
 
result.push(new SpliceOutOpportunityGenerator()); 
return result; 
}
```

