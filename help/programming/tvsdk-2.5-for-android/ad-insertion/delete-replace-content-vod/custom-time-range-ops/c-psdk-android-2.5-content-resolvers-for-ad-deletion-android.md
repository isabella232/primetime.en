---
description: You can use multiple content resolvers to handle different timeline operations.
seo-description: You can use multiple content resolvers to handle different timeline operations.
seo-title: Content resolvers for ad deletion / replacement
title: Content resolvers for ad deletion / replacement
uuid: ed168c52-ab7b-4fe6-8775-eb18018dc249
---

# Content resolvers for ad deletion / replacement{#content-resolvers-for-ad-deletion-replacement}

You can use multiple content resolvers to handle different timeline operations.

```java
public List<ContentResolver> retrieveResolvers(MediaPlayerItem item) { 
    List<ContentResolver> resolvers = new ArrayList<ContentResolver>(); 
    MediaPlayerItemConfig itemConfig = item.getConfig(); 
    if(itemConfig) { 
        CustomRangeMetadata customRanges = itemConfig.getCustomRangeMetadata(); 
        if (customRanges) { 
            List<ReplaceTimeRange> timeRanges = customRanges.getTimeRangeList(); 
 
            if (timeRanges && timeRanges.size() > 0) { 
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

