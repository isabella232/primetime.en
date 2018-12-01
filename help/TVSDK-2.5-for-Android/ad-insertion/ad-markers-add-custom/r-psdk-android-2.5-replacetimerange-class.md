---
description: The ReplaceTimeRange utility class is an extension of the TimeRange class to be used with CustomRangeMetadata.
seo-description: The ReplaceTimeRange utility class is an extension of the TimeRange class to be used with CustomRangeMetadata.
seo-title: ReplaceTimeRange class
title: ReplaceTimeRange class
uuid: 1cfb0b5e-93da-4f3e-9fc1-2ffbb71baa4a
index: y
internal: n
snippet: y
---

# ReplaceTimeRange class{#replacetimerange-class}

The ReplaceTimeRange utility class is an extension of the TimeRange class to be used with CustomRangeMetadata.

```java
public class ReplaceTimeRange extends TimeRange {
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

