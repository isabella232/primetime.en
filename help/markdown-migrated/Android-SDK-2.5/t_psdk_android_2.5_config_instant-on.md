---
description: provides methods and statuses to allow you use Instant On with a media resource.
seo-description: provides methods and statuses to allow you use Instant On with a media resource.
seo-title: Configure buffering for Instant On
title: Configure buffering for Instant On
---

# Configure buffering for Instant On

>[!NOTE]
>
>Adobe recommends using`codeph  MediaPlayerItemLoader` for InstantOn. To use `codeph  MediaPlayerItemLoader`, rather than `codeph  MediaPlayer`, see []().
>1. Confirm that the resource has loaded, and the player is prepared to play the resource.
>   
>1. Before calling `codeph  play`, call `codeph  prepareBuffer` for each `codeph  MediaPlayer` instance.
>   `codeph  prepareBuffer` enables Instant On, and  starts buffering immediately and dispatches the `codeph  BUFFERING_COMPLETED` event when the buffer is full.
>   >[!TIP]
>   >
>   >By default,`codeph  prepareBuffer` and `codeph  prepareToPlay` set up the media stream to start playing from the beginning. To start at another position, pass the position (in milliseconds) to `codeph  prepareToPlay`.
>   ```
>   @Override 
>   public void onStatusChanged(MediaPlayerStatus status) { 
>    switch (status) { 
>    case INITIALIZED: 
>    // This example starts 5 seconds into the stream. 
>    mediaPlayer.prepareToPlay(5000); 
>    break; 
>    case PREPARING: 
>    break; 
>    case PREPARED: 
>    mediaPlayer.prepareBuffer(); 
>    break; 
>    ... 
>    } 
>   }
>   ```
>   
>   
>1. When you receive the `codeph  BUFFERING_COMPLETE` event, start playing the item or display visual feedback to indicate that the content is completely buffered.
>   If you call`codeph  play`, playback should begin immediately.
>   
>   
