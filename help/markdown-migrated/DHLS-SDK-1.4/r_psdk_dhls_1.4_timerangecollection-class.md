---
---

<a id="section_D87AA7BC628D458DAB12D5247AD34B41"></a>

```
public final class TimeRangeCollection { 
 public static const MARK_RANGES:String = "mark_ranges"; 
 
 public function TimeRangeCollection(timeRanges:Vector.&lt;TimeRange&gt;) {…} 
 public function addTimeRange(timeRange:TimeRange):void {…} 
 public function toMetadata(options:Metadata):Metadata {…} 
}
```
The defined value for the type of collection are `codeph  MARK_RANGES`, `codeph  DELETE_RANGES`, and `codeph  REPLACE_RANGES`. You can create `codeph  TimeRangeCollection`s using these three types.

