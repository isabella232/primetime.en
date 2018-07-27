---
description: In certain analytics implementations, the client application may want to provide a different playhead position than the one reported by the localTime value. For example, during a LINEAR stream playback, each program’s playhead can be provided relative to it’s start time.
seo-description: In certain analytics implementations, the client application may want to provide a different playhead position than the one reported by the localTime value. For example, during a LINEAR stream playback, each program’s playhead can be provided relative to it’s start time.
seo-title: Implement custom time updates
title: Implement custom time updates
uuid: 49fda0ad-15ce-4246-b31e-408fd4c4d998
index: n
internal: n
snippet: y
translate: y
---

# Implement custom time updates


>[!TIP]
>
>Override this method only if you want to provide a different playhead position than the default position.


>1. To override the default playhead position:
>
>   ```
>   vaMetadata.currentTimeUpdateBlock = function():Number { 
>      if (currentTime == 0) { 
>          currentTime = getTimer(); 
>      } 
>      return ((getTimer() - currentTime) / 1000 + 1000); 
>   }
>   ```

>   >[!IMPORTANT]
>   >
>   >The values in this code snippet are only samples. You need to use different values for your custom playhead position.
>
