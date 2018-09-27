---
description: null
seo-description: null
seo-title: Add a QoS Provider instance to mediaPlayerItemLoader
title: Add a QoS Provider instance to mediaPlayerItemLoader
uuid: b160a688-5d5f-41e8-b3a0-c4ac68e6bf09
index: y
internal: n
snippet: y
translate: y
---

# Add a QoS Provider instance to mediaPlayerItemLoader



1. Create and attach a QoS Provider to a `mediaPlayerItemLoader` instance

   ```
   // Create an instance of QoSProvider  
   private QOSProvider _qosProvider = new QOSProvider(this._context);  
    
   // Attach the QoSProvider instance to the mediaPlayerItemLoaderInstance  
   // (before calling load API on mediaPlayerItemLoader instance)  
   _qosProvider.attachMediaPlayerItemLoader(this._loader); 
   ```

Once the playback starts, use the `_qosProvider` to get `timeToLoad` and `timeToPrepare` QoSdata. The remaining QoS metrics can be retrieved by using the `QoSProvider` attached to the `mediaPlayer`. For more information about `MediaPlayerItemLoader`, see [Load a media resource using MediaPlayerItemLoader](../../../../titlepage/content-playback-options/mediaplayer-initialize-for-video/t_media-resource-load-using-mediaplayeritemloader.md#use-mediaplayeritemloader). 