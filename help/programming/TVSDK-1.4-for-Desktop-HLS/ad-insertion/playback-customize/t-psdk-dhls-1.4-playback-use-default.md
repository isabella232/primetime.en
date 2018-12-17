---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
uuid: d8b03e69-f946-44ba-a4f8-73a5e7a18be1
index: y
internal: n
snippet: y
---

# Use the default playback behavior{#use-the-default-playback-behavior}

You can choose to use default ad behaviors.

1. To use default behaviors:

    * If you implement your own `ContentFactory` class, return a new instance of `DefaultAdPolicySelector` in your implementation of `doRetrieveAdPolicySelector`.     
    
      ```    
      public class CustomContentFactory extends ContentFactory { 
        
          //... 
          // your custom code for advertising classes 
          //... 
            
          /** 
           * @inheritDoc 
           */ 
          override protected function  
            doRetrieveAdPolicySelector(item:MediaPlayerItem):AdPolicySelector { 
              return new DefaultAdPolicySelector(item); 
          } 
      }
      ```

    * If you do not have a custom implementation for the `ContentFactory` class, TVSDK uses `DefaultAdPolicySelector`.

