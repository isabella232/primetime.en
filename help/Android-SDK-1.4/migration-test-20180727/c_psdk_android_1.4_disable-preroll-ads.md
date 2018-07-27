---
description: null
seo-description: null
seo-title: Disable pre-roll ads
title: Disable pre-roll ads
uuid: fc14961a-8c6c-4693-bdee-f3cd36223f9f
index: n
internal: n
snippet: y
translate: y
---

# Disable pre-roll ads

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

