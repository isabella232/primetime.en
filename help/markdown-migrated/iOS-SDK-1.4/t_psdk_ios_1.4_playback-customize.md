---
description: You can customize or override default ad behaviors.
seo-description: You can customize or override default ad behaviors.
seo-title: Set up customized playback
title: Set up customized playback
---

# Set up customized playback

Before you can customize or override ad behaviors, register the ad policy instance with .

To customize ad behaviors, do one of the following:

* Conform to the `codeph  PTAdPolicySelector` protocol and implement all the required policy selection methods.
  This option is recommended if you need to override **all** the default ad behaviors.
  
  
* Override the `codeph  PTDefaultAdPolicySelector` class and provide implementations for only those behaviors that require customization.
  This option is recommended if you need to override only **some** of the default behaviors.
  
  
For both options, complete the following tasks:

>1. Register the policy instance to be used by  through the client factory.
>   >[!NOTE] {type="attention"}
>   >
>   >Custom ad policies that are registered at the beginning of playback are cleared when the`codeph  PTMediaPlayer` instance is deallocated. Your application must register a policy selector instance each time a new playback session is created.
>   
>       
>       
>       ```
>       // Create an instance of the custom policy selector 
>       PTS5MinuteSkipBreakPolicySelector *adPolicySelector 
>        = [[[PTS5MinuteSkipBreakPolicySelector alloc] initWithMediaPlayer:self.player] autorelease]; 
>        
>       // register this instance 
>       [[PTDefaultMediaPlayerClientFactory defaultFactory] registerAdPolicySelector:adPolicySelector];
>       ```
>       
>   
>1. Implement your customizations.
>   
>   
