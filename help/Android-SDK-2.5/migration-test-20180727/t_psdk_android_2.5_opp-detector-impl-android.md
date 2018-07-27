---
description: You can implement your own opportunity generators by implementing the OpportunityGenerator class.
seo-description: You can implement your own opportunity generators by implementing the OpportunityGenerator class.
seo-title: Implement a custom opportunity generator
title: Implement a custom opportunity generator
uuid: 33965d11-c557-4f8a-81ae-b61fa74302f4
index: n
internal: n
snippet: y
translate: y
---

# Implement a custom opportunity generator


>1. Implement your custom ` ContentFactory` by implementing the ` ContentFactory` interface and overriding ` retrieveGenerators`.
>   For example: >
>   ```
>   java>   class MyContentFactory extends ContentFactory { 
>       @Override 
>       public List&lt;OpportunityGenerator&gt; retrieveGenerators(MediaPlayerItem item) { 
>           List&lt;OpportunityGenerator&gt; generators = new ArrayList&lt;OpportunityGenerator&gt;(); 
>           generators.add(MyOpportunityGenerator(item)); 
>           return generators; 
>       } 
>       ... 
>   }
>   ```

>
>1. Register the ` ContentFactory` to the ` MediaPlayer`.
>   For example: >
>   ```
>   java>   // register the custom content factory with media player 
>   MediaPlayerItemConfig config =  new MediaPlayerItemConfig(); 
>   config.setAdvertisingFactory(new MyContentFactory()); 
>    
>   // this config will should be later passed while loading the resource 
>   mediaPlayer.replaceCurrentResource(resource, config); 
>    
>   // OR use MediaPlayerItemLoader to pre-load a resource 
>   id = 23; 
>   itemLoader.load(resource, id, config);
>   ```

>
>1. Create a custom opportunity generator class that implements the ` OpportunityGenerator` class.
>
>   ```
>   java>   public class CustomOpportunityGenerator implements OpportunityGenerator  
>   {...}
>   ```
>
>   >1. In the custom opportunity generator, override ` doConfigure`, ` doUpdate` and ` doCleanup`:
>   >
>   >   ```
>   >   java>   >   @Override 
>   >    public void configure(MediaPlayerItem item, Context context,  
>   >    OpportunityGeneratorClient client, AdSignalingMode mode, long playhead, TimeRange playbackRange) { 
>   >   } 
>   >    
>   >   protected void update(long playhead, TimeRange playbackRange){ 
>   >   } 
>   >    
>   >   protected void cleanup(){ 
>   >   }
>   >   ```

>   >   To obtain the timed metadata: >   >
>   >   ```
>   >   java>   >   List&lt;TimedMetadata&gt; tList = getItem().getTimedMetadata(); 
>   >   
>   >   ```

>   >
>   >1. For each ` TimedMetadata` or group of ` TimedMetadata`, create an opportunity with the following attributes:
>   >
>   >   ```
>   >   java>   >   Opportunity( 
>   >     String id,                      // Can be id from timedMetadata  
>   >     Placement placementInformation, // Placement object containing Type, time, duration 
>   >     Metadata metadataSettings,      // Ad metadata with targeting params sent to the ad provider 
>   >     Metadata customParams           // Metadata for customizing resolving and/or tracking process. 
>   >   ); 
>   >   
>   >   ```
>   >
>   >1. For each opportunity created, call ` resolve` on the ` OpportunityGeneratorClient:getClient().resolve(opportunity);`.
