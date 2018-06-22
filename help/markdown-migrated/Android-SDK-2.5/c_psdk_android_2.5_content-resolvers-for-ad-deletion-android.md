---
description: You can use multiple content resolvers to handle different timeline operations.
seo-description: You can use multiple content resolvers to handle different timeline operations.
seo-title: Content resolvers for ad deletion / replacement
title: Content resolvers for ad deletion / replacement
---

# Content resolvers for ad deletion / replacement


```java
public List&lt;ContentResolver&gt; retrieveResolvers(MediaPlayerItem item) { 
 List&lt;ContentResolver&gt; resolvers = new ArrayList&lt;ContentResolver&gt;(); 
 MediaPlayerItemConfig itemConfig = item.getConfig(); 
 if(itemConfig) { 
 CustomRangeMetadata customRanges = itemConfig.getCustomRangeMetadata(); 
 if (customRanges) { 
 List&lt;ReplaceTimeRange&gt; timeRanges = customRanges.getTimeRangeList(); 
 
 if (timeRanges &amp;&amp; timeRanges.size() &gt; 0) { 
 //CustomRangeResolver is activated by the presence of CustomRanges 
 resolvers.add(new CustomRangeResolver()); 
 } 
 } 
 AdvertisingMetadata metadata = itemConfig.getAdvertisingMetadata(); 
 if (metadata) { 
 if (metadata instanceOf AuditudeSettings) 
 resolvers.add(new AuditudeResolver(getContext()); 
 } 
 } 
 //Add your custom resolver if any 
 resolvers.add(MyOpportunityGenerator(item)); 
 return resolvers; 
} 

```

