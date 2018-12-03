---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
uuid: 22a4ce2e-6b0b-42fb-a6e7-db8021712fda
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

