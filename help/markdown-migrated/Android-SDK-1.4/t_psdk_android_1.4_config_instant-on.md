---
description: With instant on, users can switch channels and the playback starts immediately without waiting time. When you enable instant on, buffers one or more channels before playback begins.
seo-description: With instant on, users can switch channels and the playback starts immediately without waiting time. When you enable instant on, buffers one or more channels before playback begins.
seo-title: Configure buffering for instant-on playback
title: Configure buffering for instant-on playback
---

# Configure buffering for instant-on playback

>1. Confirm that the resource has loaded and is ready for playing by verifying that the state is PREPARED.
>   
>1. Before calling `codeph  play`, call `codeph  prepareBuffer` for each `codeph  MediaPlayer` instance.
>   This enables instant on, which means that starts buffering without actually playing the media resource.  dispatches the `codeph  BUFFERING_COMPLETED` event when the buffer is full.
>   >[!NOTE]
>   >
>   >By default,`codeph  prepareBuffer` and `codeph  prepareToPlay` set up the media stream to start playing from the beginning. To start at another position, pass the position (in milliseconds) into `codeph  prepareToPlay`.
>   ```java
>   @Override 
>   public void onStateChanged(MediaPlayer.PlayerState state, 
>    MediaPlayerNotification notification) { 
>    switch (state) { 
>    case INITIALIZED: 
>    // By default, prepareToPlay and prepareBuffer buffer and start playing 
>    // from the beginning of the stream. To start at another position, 
>    // pass it into prepareToPlay. This example starts 5 seconds into the stream. 
>    _mediaPlayer.prepareToPlay(5000); 
>    break; 
>    case PREPARING: 
>    break; 
>    case PREPARED: 
>    _mediaPlayer.prepareBuffer(); 
>    break; 
>    ... 
>    } 
>   }
>   ```
>   
>   
>1. When you receive the `codeph  BUFFERING_COMPLETE` event, start playing the item or display visual feedback to indicate that the content is completely buffered.
>   If you call`codeph  play`, playback should begin immediately.
>   ```java
>   void onBufferPrepared(const psdk::PSDKEvent *ev) { 
>       mediaPlayer-&gt;play(); 
>   }
>   ```
>   
>   
>   
