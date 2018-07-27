---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
uuid: 4a40103a-0fa2-4c78-b7b1-59e3e1e7d311
index: n
internal: n
snippet: y
translate: y
---

# Use the default playback behavior


>1. To use default behaviors:
>    * If you implement your own ` ContentFactory` class, return a new instance of ` DefaultAdPolicySelector` in your implementation of ` doRetrieveAdPolicySelector`. >    
>      ```
>      public class CustomContentFactory extends ContentFactory { 
>        
>          //... 
>          // your custom code for advertising classes 
>          //... 
>            
>          /** 
>           * @inheritDoc 
>           */ 
>          override protected function  
>            doRetrieveAdPolicySelector(item:MediaPlayerItem):AdPolicySelector { 
>              return new DefaultAdPolicySelector(item); 
>          } 
>      }
>      ```

>    * If you do not have a custom implementation for the ` ContentFactory` class,  <!-- PH element: phrases/primetime-sdk-name --> uses ` DefaultAdPolicySelector`.
