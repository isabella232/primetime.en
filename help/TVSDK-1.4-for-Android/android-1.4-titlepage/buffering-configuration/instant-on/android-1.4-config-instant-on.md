---
description: With instant on, users can switch channels and the playback starts immediately without waiting time. When you enable instant on, TVSDK buffers one or more channels before playback begins.
seo-description: With instant on, users can switch channels and the playback starts immediately without waiting time. When you enable instant on, TVSDK buffers one or more channels before playback begins.
seo-title: Configure buffering for instant-on playback
title: Configure buffering for instant-on playback
uuid: daa64f60-633a-4b4d-a34b-a7ad78100ecc
index: y
internal: n
snippet: y
---

# Configure buffering for instant-on playback{#configure-buffering-for-instant-on-playback}

With instant on, users can switch channels and the playback starts immediately without waiting time. When you enable instant on, TVSDK buffers one or more channels before playback begins.

1. Confirm that the resource has loaded and is ready for playing by verifying that the state is PREPARED.
1. Before calling `play`, call `prepareBuffer` for each `MediaPlayer` instance.

   This enables instant on, which means that TVSDK starts buffering without actually playing the media resource. TVSDK dispatches the `BUFFERING_COMPLETED` event when the buffer is full.

   >[!NOTE]
   >
   >By default, `prepareBuffer` and `prepareToPlay` set up the media stream to start playing from the beginning. To start at another position, pass the position (in milliseconds) into `prepareToPlay`.

   ```java
   @Override 
   public void onStateChanged(MediaPlayer.PlayerState state,  
                              MediaPlayerNotification notification) { 
       switch (state) { 
           case INITIALIZED: 
               // By default, prepareToPlay and prepareBuffer buffer and start playing 
               // from the beginning of the stream. To start at another position, 
               // pass it into prepareToPlay. This example starts 5 seconds into the stream. 
               _mediaPlayer.prepareToPlay(5000); 
               break; 
           case PREPARING: 
               break; 
           case PREPARED: 
               _mediaPlayer.prepareBuffer(); 
               break; 
           ... 
       } 
   }
   ```

1. When you receive the `BUFFERING_COMPLETE` event, start playing the item or display visual feedback to indicate that the content is completely buffered.

   If you call `play`, playback should begin immediately. 

   ```java
   void onBufferPrepared(const psdk::PSDKEvent *ev) { 
       mediaPlayer->play(); 
   }
   ```

