---
description: In some analytics implementations, the client application might want to provide a different playhead position than the position that is reported by the TVSDK’s localTime value. For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.
seo-description: In some analytics implementations, the client application might want to provide a different playhead position than the position that is reported by the TVSDK’s localTime value. For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.
seo-title: Implement custom time updates
title: Implement custom time updates
uuid: a5b76b86-74bb-4a3f-bdb5-115bcd8c73ba
index: y
internal: n
snippet: y
---

# Implement custom time updates{#implement-custom-time-updates}

In some analytics implementations, the client application might want to provide a different playhead position than the position that is reported by the TVSDK’s localTime value. For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.

>[!TIP]
>
>Override this method only if you want to provide a playhead position that is different from the default position.

1. To override the default playhead position:

   ```
   vaTrackingMetadata.currentTimeUpdateBlock = ^CMTime () { 
       NSInteger random = arc4random() % 500;  
       return CMTimeMakeWithSeconds(random, 1); 
   };
   ```

   >[!IMPORTANT]
   >
   >In this code sample, 500 is only a sample value. You need to use a different value for your custom playhead position.

