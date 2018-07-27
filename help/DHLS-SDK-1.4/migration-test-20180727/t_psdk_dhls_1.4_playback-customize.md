---
description: You can customize or override ad behaviors.
seo-description: You can customize or override ad behaviors.
seo-title: Set up customized playback
title: Set up customized playback
uuid: dfcbcfe4-4e7d-41cc-9549-bf43629b63bf
index: n
internal: n
snippet: y
translate: y
---

# Set up customized playback

Before you can customize or override ad behaviors, register the ad policy instance with  <!-- PH element: phrases/primetime-sdk-name --> .
To customize ad behaviors, do one of the following:

* Implement the ` AdPolicySelector` interface and all its methods. This option is recommended if you need to override **all** the default ad behaviors. 

* Extend the ` DefaultAdPolicySelector` class and provide implementations for only those behaviors that require customization. This option is recommended if you need to override only **some** of the default behaviors. 

For both options, complete the following tasks:

>1. Implement your own custom ad policy selector.

>    
>       ```
>       public class CustomAdPolicySelector implements AdPolicySelector { 
>           // your own customization here 
>       }
>       ```
>1. Extend the content factory to use the custom ad policy selector.

>    
>       ```
>       public class CustomContentFactory extends DefaultContentFactory { 
>           /** 
>            * @inheritDoc 
>            */ 
>           override protected function doRetrieveAdPolicySelector(item:MediaPlayerItem):AdPolicySelector { 
>               return new CustomAdPolicySelector(item); 
>           } 
>       }
>       ```
>    
>       ```
>       psdkutils::PSDKSharedPointer&lt;psdk::ContentFactory&gt; factory; 
>       psdkFactory-&gt;createDefaultContentFactory(&amp;factory); 
>       psdkutils::PSDKSharedPointer&lt;psdk::AdPolicySelector&gt; defaultAdPolicySelector; 
>       factory-&gt;retrieveAdPolicySelector(item, &amp;defaultAdPolicySelector);
>       ```
>1. Register the new content factory to be used by  <!-- PH element: phrases/primetime-sdk-name --> in the advertising workflow.

>    
>       ```
>       PSDKConfig.advertisingFactory = new CustomContentFactory();
>       ```

>   >[!TIP]
>   >
>   >If the custom content factory was registered for a specific stream through the ` MediaPlayerItemConfig` class, it will be cleared when the ` MediaPlayer` instance is deallocated. Your application must register it each time a new playback session is created. 
>
