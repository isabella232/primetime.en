---
description: null
seo-description: null
seo-title: Signaling mode and time range
title: Signaling mode and time range
uuid: 7d653e85-d0c1-4cac-ac51-d5b314d46095
index: n
internal: n
snippet: y
translate: y
---

# Signaling mode and time range





|   | MARK  | DELETE  | REPLACE  |
|---|---|---|---|
|  ` CustomRange OpportunityGenerator`  | 
```
(range.begin,  
 range.end)
```
| 
```
(range.begin,  
 range.end)
```
| 
```
(range.begin,  
 range.end,  
 replaceDuration)
```
|
|  ` ServerMap` Signaling Mode  | 
```
placement =  
  new Placement(  
    PlacementType.CUSTOM_RANGE,  
    range.begin,  
    range.end -  
    range.begin, 
    PlacementMode.MARK );
```
| 
```
placement =  
  new Placement(  
    PlacementType.CUSTOM_RANGE,  
    range.begin,  
    range.end - range.begin,  
    PlacementMode.DELETE );
```
| N/A (automatic CustomRange signaling mode)  |
|  ` ManifestCue` Signaling Mode  | 
```
placement =  
new Placement( 
    PlacementType.CUSTOM_RANGE, 
    range.begin, 
    range.end - range.begin, 
    PlacementMode.MARK 
);
```
| 
```
placement =  
  new Placement( 
    PlacementType.CUSTOM_RANGE, 
    range.begin, 
    range.end - range.begin, 
    PlacementMode.DELETE 
);
```
| N/A (automatic CustomRange signaling mode)  |
|  ` CustomRange` Signaling Mode  | 
```
placement =  
  new Placement( 
    PlacementType.CUSTOM_RANGE, 
    range.begin, 
    range.end - range.begin, 
    PlacementMode.MARK 
);
```
| 
```
placement =  
  new Placement( 
    PlacementType.CUSTOM_RANGE, 
    range.begin, 
    range.end - range.begin, 
    PlacementMode.DELETE 
);
```
| 
```
placement1 =  
  new Placement( 
    PlacementType.CUSTOM_RANGE, 
    range.begin, 
    range.end - range.begin, 
    PlacementMode.MARK 
); 
placement2 = placement =  
  new Placement(/ 
    PlacementType.MID_ROLL( 
    PlacementType.PRE_ROLL), 
    rangeDuration, 
    placementMode 
);
```
|





|   | MARK  | DELETE  | REPLACE  |
|---|---|---|---|
|  ` AdSignalingMode OpportunityGenerator`  | 
```
(range.begin,  
 range.end)
```
| 
```
(range.begin,  
 range.end)
```
| 
```
(range.begin,  
 range.end,  
 replaceDuration)
```
|
|  ` SeverMap` Signaling Mode  | Not present (ad is disabled).  | 
```
placement =  
 new Placement( 
PlacementType.SERVER_MAP, 
Placement.UNKNOWN_TIME, 
Placement.UNKNOWN_DURATION, 
PlacementMode.DEFAULT);
```
| N/A (automatic ` CustomRange` signaling mode)  |
|  ` ManifestCue` Signaling Mode  | Not present (ad is disabled).  | 
```
placement =  
 new Placement( 
PlacementType.PRE_ROLL, 
playhead, 
Placement.UNKNOWN_DURATION, 
PlacementMode.DEFAULT);
```
| N/A (automatic ` CustomRange` signaling mode)  |
|  ` CustomRange` Signaling Mode  | Not present (ad is disabled).  | None  | None (taken care of in ` CustomRangeOpportunityGenerator`)  |

