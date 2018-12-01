---
description: In some analytics implementations, the client application might want to provide a different playhead position than the position reported by the Browser TVSDK localTime value.
seo-description: In some analytics implementations, the client application might want to provide a different playhead position than the position reported by the Browser TVSDK localTime value.
seo-title: Implement custom time updates
title: Implement custom time updates
uuid: 6e1108f1-d665-432f-b196-cff87bb07860
index: y
internal: n
snippet: y
---

# Implement custom time updates{#implement-custom-time-updates}

In some analytics implementations, the client application might want to provide a different playhead position than the position reported by the Browser TVSDK localTime value.

For example, during a linear stream playback, each program’s playhead can be provided relative to its start time.

>[!TIP]
>
>Override this method only if you want to provide a playhead position other than the default position.

To override the default playhead position: 

```js
vaMetadata.currentTimeUpdateBlock = function() { 
       return playerPositionInSeconds; 
}; 

```

>[!IMPORTANT]
>
>The values in this code snippet are only samples. You need to use different values for your custom playhead position.

