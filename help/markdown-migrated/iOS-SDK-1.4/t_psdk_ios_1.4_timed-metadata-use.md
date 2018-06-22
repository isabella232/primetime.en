---
description: You can use TimedMetadata when the current playback time matches the start time.
seo-description: You can use TimedMetadata when the current playback time matches the start time.
seo-title: Use timed metadata
title: Use timed metadata
---

# Use timed metadata

To use these saved `codeph  PTTimedMetadata` objects during playback, use the saved  from [ Store timed-metadata objects as they are dispatched ](t_psdk_ios_1.4_timed-metadata-store.md#task_timed_metadata_store).

>1. Extract and update the current playback time from this notification and find all of the `codeph  PTTimedMetadata` objects with start times that match the current playback time.
>   You can use these objects to complete various actions.
>   
>   For example:
>   ```
>   - (void) onMediaPlayerTimeChange:(NSNotification *)notification 
>   { 
>    CMTimeRange seekableRange = self.player.seekableRange; 
>    if (CMTIMERANGE_IS_VALID(seekableRange)) 
>    { 
>    int currentTime = (int) CMTimeGetSeconds(self.player.currentTime); 
>    NSArray *allKeys = timedMetadataCollection ? [timedMetadataCollection allKeys] : [NSArray array]; 
>    NSMutableArray *timedMetadatasToDelete = [[[NSMutableArray alloc] init] autorelease]; 
>    int count = [allKeys count]; 
>    
>    for (int i=count - 1; i &gt; -1; i--) 
>    { 
>    NSNumber *currTimedMetadataTime = allKeys[i]; 
>    if ([currTimedMetadataTime integerValue] == currentTime) 
>    { 
>    /* 
>    Use the timed metadata here and remove it from the collection. 
>    */ 
>    NSLog (@"IN PLAYBACK TIME %i TO EXECUTE TIMEDMETADATA %@ scheduled at time %f",currentTime,currTimedMetadata.name,CMTimeGetSeconds(currTimedMetadata.time)); 
>    
>    PTTimedMetadata *currTimedMetadata = [timedMetadataCollection objectForKey:currTimedMetadataTime]; 
>    [timedMetadatasToDelete addObject:currTimedMetadataTime]; 
>    } 
>    } 
>    
>    for (int i=0; i&lt;[timedMetadatasToDelete count]; i++) 
>    { 
>    NSNumber *timedMetadataToDelete = timedMetadatasToDelete[i]; 
>    [timedMetadataCollection removeObjectForKey:timedMetadataToDelete]; 
>    } 
>    } 
>   }
>   ```
>   
>   
>   
>1. Periodically flush stale `codeph  PTTimedMetadata` instances from the list to prevent memory from continuously growing.
>   
>   
