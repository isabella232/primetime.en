---
description: To receive notifications about tags in the manifest, implement the appropriate event listener(s).
seo-description: To receive notifications about tags in the manifest, implement the appropriate event listener(s).
seo-title: Add listeners for timed metadata notifications
title: Add listeners for timed metadata notifications
---

# Add listeners for timed metadata notifications

You can monitor timed metadata by listening for the following events, which notify your application of related activity:
* `codeph  onTimedMetadata`: Each time a unique subscribed tag is identified during parsing of the content,  prepares a new `codeph  TimedMetadata` object and dispatches this event.
  The object contains the name of the tag to which you subscribed, the local time in the playback where this tag will appear, and other data.
  
  

>1. Listen for events.
>   ```java
>   private final TimedMetadataEventListener timedMetadataEventListener = 
>    new TimedMetadataEventListener() { 
>    @Override 
>    public void onTimedMetadata(TimedMetadataEvent timedMetadataEvent) { 
>    TimedMetadata timedMetadata = timedMetadataEvent.getTimedMetadata(); 
>    
>    TimedMetadata.Type type = timedMetadata.getType(); 
>    if (type.equals(TimedMetadata.Type.ID3)){ 
>    Metadata metadata = timedMetadata.getMetadata(); 
>    Set&lt;String&gt; keys = metadata.keySet(); 
>    for (String key : keys) { 
>    String value = metadata.getValue(key); 
>    } 
>    } else if (_mediaPlayer.getPlaybackRange() != 
>    null &amp;&amp; _mediaPlayer.getPlaybackRange().getDuration() &gt; 0) { 
>    displayRanges(); 
>    } 
>    } 
>   }; 
>   
>   ```
>   
>   
>   
