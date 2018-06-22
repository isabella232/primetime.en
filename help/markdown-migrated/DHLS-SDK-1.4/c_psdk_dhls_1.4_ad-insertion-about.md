---
description: 
seo-description: 
seo-title: Disable pre-roll ads
title: Disable pre-roll ads
---

# Disable pre-roll ads

An `term  ad break` contains one or more ads that play in sequence.  inserts ads in the main content as members of one or more ad breaks.

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

