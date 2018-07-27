---
description: The ReplaceTimeRange utility class is an extension of the TimeRange class to be used with CustomRangeMetadata.
seo-description: The ReplaceTimeRange utility class is an extension of the TimeRange class to be used with CustomRangeMetadata.
seo-title: ReplaceTimeRange class
title: ReplaceTimeRange class
uuid: eee77bb8-85ad-4376-83a3-b2d3a8b4bb63
index: n
internal: n
snippet: y
translate: y
---

# ReplaceTimeRange class





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
