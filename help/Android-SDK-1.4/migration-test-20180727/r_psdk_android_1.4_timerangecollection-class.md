---
description: The TimeRangeCollection utility class abstracts the notion of an ordered collection of TimeRange specifications and provides services to translate itself into a Metadata instance.
seo-description: The TimeRangeCollection utility class abstracts the notion of an ordered collection of TimeRange specifications and provides services to translate itself into a Metadata instance.
seo-title: TimeRangeCollection class
title: TimeRangeCollection class
uuid: fd857224-ba8a-40d1-8044-ed2e7ca8b0f9
index: n
internal: n
snippet: y
translate: y
---

# TimeRangeCollection class


<a id="section_D87AA7BC628D458DAB12D5247AD34B41"></a>


```
javapublic final class TimeRangeCollection {
    // default constructor method
    public TimeRangeCollection(Type type) {...}

    // the list of timerange specifications provided at construction time 
    public TimeRangeCollection(Type type, List&lt;TimeRange&gt; timeRanges) {...}

    // timerange specs can also be added later
    public void addTimeRange(TimeRange timeRange) {...}

    // translate the set of timerange specs into a Metadata instance 
    public Metadata toMetadata(Metadata options) {...}
}

```
The values that are currently defined by this enumeration are `MARK_RANGES`, `DELETE_RANGES`, and `REPLACE_RANGES`. You can create `TimeRangeCollection` objects using these three types. 
