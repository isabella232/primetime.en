---
description: To receive notifications about tags in the manifest, register the appropriate event listener(s).
seo-description: To receive notifications about tags in the manifest, register the appropriate event listener(s).
seo-title: Add listeners for timed metadata notifications
title: Add listeners for timed metadata notifications
---

# Add listeners for timed metadata notifications

You can monitor timed metadata by listening for the following events, which notify your application of related activity:
* `codeph  MediaPlayerItemEvent.ITEM_CREATED`: The initial list of `codeph  TimedMetadata` objects is available after the `codeph  MediaPlayerItem` is created.
  This event notifies your application when this happens.
  
  
* `codeph  MediaPlayerItemEvent.ITEM_UPDATED`: For live/linear streams where the manifest/playlist refreshes periodically, additional custom tags might appear in the updated playlist/manifest, so additional `codeph  TimedMetadata` objects might be added to the `codeph  MediaPlayerItem.timedMetadata` property.
  This event notifies your application when this happens.
  
  
* `codeph  TimedMetadataEvent.TIMED_METADATA_AVAILABLE`: Each time a new `codeph  TimedMetadata` object is created, this event is dispatched by the MediaPlayer.
  This event is not dispatched for the `codeph  TimedMetadata` object created during the initialization phase.
  
  

>1. Implement the appropriate listeners.
>   ```
>   private function onItemCreated(event:MediaPlayerItemEvent):void { 
>    var timedMetadataCollection:Vector.&lt;TimedMetadata&gt; = event.item.timedMetadata; 
>    // process the timed metadata collection 
>   } 
>    
>   private function onItemUpdated(event:MediaPlayerItemEvent):void { 
>    var timedMetadataCollection:Vector.&lt;TimedMetadata&gt; = event.item.timedMetadata; 
>    // process the timed metadata collection 
>   } 
>    
>   private function onTimedMetadataAvailable(event:TimedMetadataEvent):void { 
>    var timedMetadata:TimedMetadata = event.timedMetadata; 
>    // process timed metadata 
>   }
>   ```
>   
>   
>1. Register the event listeners.
>       
>       ```
>       player.addEventListener(MediaPlayerItemEvent.ITEM_CREATED, onItemCreated); 
>       player.addEventListener(MediaPlayerItemEvent.ITEM_UPDATED, onItemUpdated); 
>       player.addEventListener(TimedMetadataEvent.TIMED_METADATA_AVAILABLE, 
>        onTimedMetadataAvailable);
>       ```
>       
>   
>   
