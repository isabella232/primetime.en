---
description: The ReplaceTimeRange utility class is an extension of the TimeRange class to be used with CustomRangeMetadata.
seo-description: The ReplaceTimeRange utility class is an extension of the TimeRange class to be used with CustomRangeMetadata.
seo-title: ReplaceTimeRange class
title: ReplaceTimeRange class
uuid: dd749e2b-fd95-48da-9eeb-9f8f79634c6c
index: y
internal: n
snippet: y
translate: y
---

# ReplaceTimeRange class

The ReplaceTimeRange utility class is an extension of the TimeRange class to be used with CustomRangeMetadata.




```
javapublic class ReplaceTimeRange extends TimeRange {
    // Default constructor method
    public ReplaceTimeRange() { 
        ... 
    }

    // Details of begining, duration and replaceDuration 
    // provided at construction time 
    public ReplaceTimeRange(long begin, long duration, long replaceDuration) { 
        ... 
    }

    // Replace duration
    public long getReplaceDuration() { 
        ... 
    }
}

```
