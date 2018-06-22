---
description: You can implement your own opportunity generators by implementing the OpportunityGenerator class.
seo-description: You can implement your own opportunity generators by implementing the OpportunityGenerator class.
seo-title: Implement a custom opportunity generator
title: Implement a custom opportunity generator
---

# Implement a custom opportunity generator

>1. Implement your custom `codeph  ContentFactory` by implementing the `codeph  ContentFactory` interface and overriding `codeph  retrieveGenerators`.
>   For example:
>   ```java
>   class MyContentFactory extends ContentFactory { 
>    @Override 
>    public List&lt;OpportunityGenerator&gt; retrieveGenerators(MediaPlayerItem item) { 
>    List&lt;OpportunityGenerator&gt; generators = new ArrayList&lt;OpportunityGenerator&gt;(); 
>    generators.add(MyOpportunityGenerator(item)); 
>    return generators; 
>    } 
>    ... 
>   }
>   ```
>   
>   
>   
>1. Register the `codeph  ContentFactory` to the `codeph  MediaPlayer`.
>   For example:
>   ```java
>   // register the custom content factory with media player 
>   MediaPlayerItemConfig config = new MediaPlayerItemConfig(); 
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
>   
>   
>1. Create a custom opportunity generator class that implements the `codeph  OpportunityGenerator` class.
>   ```java
>   public class CustomOpportunityGenerator implements OpportunityGenerator 
>   {...}
>   ```
>   
>   >1. In the custom opportunity generator, override `codeph  doConfigure`, `codeph  doUpdate` and `codeph  doCleanup`:
>   >   
>   >   ```java
>   >   @Override 
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
>   >   
>   >   To obtain the timed metadata:
>   >   ```java
>   >   List&lt;TimedMetadata&gt; tList = getItem().getTimedMetadata(); 
>   >   
>   >   ```
>   >   
>   >   
>   >   
>   >1. For each `codeph  TimedMetadata` or group of `codeph  TimedMetadata`, create an opportunity with the following attributes:
>   >   ```java
>   >   Opportunity( 
>   >    String id, // Can be id from timedMetadata 
>   >    Placement placementInformation, // Placement object containing Type, time, duration 
>   >    Metadata metadataSettings, // Ad metadata with targeting params sent to the ad provider 
>   >    Metadata customParams // Metadata for customizing resolving and/or tracking process. 
>   >   ); 
>   >   
>   >   ```
>   >   
>   >   
>   >1. For each opportunity created, call `codeph  resolve` on the `codeph  OpportunityGeneratorClient:getClient().resolve(opportunity);`.
>   >   
>   >   
>   
>   
