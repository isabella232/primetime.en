---
description: null
seo-description: null
seo-title: Add a QoS Provider instance to mediaPlayerItemLoader
title: Add a QoS Provider instance to mediaPlayerItemLoader
uuid: 7d1f9215-bce8-4fe4-aa46-1e13435107f2
index: n
internal: n
snippet: y
translate: y
---

# Add a QoS Provider instance to mediaPlayerItemLoader



>1. Create and attach a QoS Provider to a ` mediaPlayerItemLoader` instance
>
>   ```
>   // Create an instance of QoSProvider  
>   private QOSProvider _qosProvider = new QOSProvider(this._context);  
>    
>   // Attach the QoSProvider instance to the mediaPlayerItemLoaderInstance  
>   // (before calling load API on mediaPlayerItemLoader instance)  
>   _qosProvider.attachMediaPlayerItemLoader(this._loader); 
>   ```
>
