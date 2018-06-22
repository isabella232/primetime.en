---
---

<a id="section_D87AA7BC628D458DAB12D5247AD34B41"></a>

```java
public final class TimeRangeCollection {
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
The values that are currently defined by this enumeration are `codeph MARK_RANGES`, `codeph DELETE_RANGES`, and `codeph REPLACE_RANGES`. You can create `codeph TimeRangeCollection` objects using these three types.

