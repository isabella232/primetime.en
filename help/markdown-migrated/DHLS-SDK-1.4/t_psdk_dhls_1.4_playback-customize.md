---
description: You can customize or override ad behaviors.
seo-description: You can customize or override ad behaviors.
seo-title: Set up customized playback
title: Set up customized playback
---

# Set up customized playback

Before you can customize or override ad behaviors, register the ad policy instance with .

To customize ad behaviors, do one of the following:

* Implement the `codeph  AdPolicySelector` interface and all its methods.
  This option is recommended if you need to override **all** the default ad behaviors.
  
  
* Extend the `codeph  DefaultAdPolicySelector` class and provide implementations for only those behaviors that require customization.
  This option is recommended if you need to override only **some** of the default behaviors.
  
  
For both options, complete the following tasks:

>1. Implement your own custom ad policy selector.
>       
>       ```
>       public class CustomAdPolicySelector implements AdPolicySelector { 
>        // your own customization here 
>       }
>       ```
>       
>   
>1. Extend the content factory to use the custom ad policy selector.
>       
>       ```
>       public class CustomContentFactory extends DefaultContentFactory { 
>        /** 
>        * @inheritDoc 
>        */ 
>        override protected function doRetrieveAdPolicySelector(item:MediaPlayerItem):AdPolicySelector { 
>        return new CustomAdPolicySelector(item); 
>        } 
>       }
>       ```
>       
>       ```
>       psdkutils::PSDKSharedPointer&lt;psdk::ContentFactory&gt; factory; 
>       psdkFactory-&gt;createDefaultContentFactory(&amp;factory); 
>       psdkutils::PSDKSharedPointer&lt;psdk::AdPolicySelector&gt; defaultAdPolicySelector; 
>       factory-&gt;retrieveAdPolicySelector(item, &amp;defaultAdPolicySelector);
>       ```
>       
>   
>1. Register the new content factory to be used by  in the advertising workflow.
>       
>       ```
>       PSDKConfig.advertisingFactory = new CustomContentFactory();
>       ```
>       
>   >[!TIP]
>   >
>   >If the custom content factory was registered for a specific stream through the`codeph  MediaPlayerItemConfig` class, it will be cleared when the `codeph  MediaPlayer` instance is deallocated. Your application must register it each time a new playback session is created.
>   
>   
>   
