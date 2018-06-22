---
description: 
seo-description: 
seo-title: Add a QoS Provider instance to mediaPlayerItemLoader
title: Add a QoS Provider instance to mediaPlayerItemLoader
---

# Add a QoS Provider instance to mediaPlayerItemLoader



>1. Create and attach a QoS Provider to a `codeph  mediaPlayerItemLoader` instance
>   ```
>   // Create an instance of QoSProvider 
>   private QOSProvider _qosProvider = new QOSProvider(this._context); 
>    
>   // Attach the QoSProvider instance to the mediaPlayerItemLoaderInstance 
>   // (before calling load API on mediaPlayerItemLoader instance) 
>   _qosProvider.attachMediaPlayerItemLoader(this._loader);
>   ```
>   
>   
>   
