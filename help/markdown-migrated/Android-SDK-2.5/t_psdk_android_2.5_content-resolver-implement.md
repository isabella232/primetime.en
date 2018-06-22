---
description: You can implement your own content resolvers based on the default resolvers.
seo-description: You can implement your own content resolvers based on the default resolvers.
seo-title: Implement a custom content resolver
title: Implement a custom content resolver
---

# Implement a custom content resolver

When  generates a new opportunity, it iterates through the registered content resolvers looking for one that is capable of resolving that opportunity. The first one that returns `codeph  true` is selected to resolve the opportunity. If no content resolver is capable, that opportunity is skipped. Because the content resolving process is usually asynchronous, the content resolver is responsible for notifying  when the process has completed.

>1. Implement your own custom `codeph  ContentFactory`, by extending the `codeph  ContentFactory` interface and overriding `codeph  retrieveResolvers`.
>   For example:
>   ```java
>   class MyContentFactory extends ContentFactory { 
>    @Override 
>    public List&lt;ContentResolver&gt; retrieveResolvers(MediaPlayerItem item) { 
>    List&lt;ContentResolver&gt; resolvers = new ArrayList&lt;ContentResolver&gt;(); 
>    MediaPlayerItemConfig itemConfig = item.getConfig(); 
>    if(itemConfig) { 
>    CustomRangeMetadata customRanges = itemConfig.getCustomRangeMetadata(); 
>    if (customRanges) { 
>    List&lt;ReplaceTimeRange&gt; timeRanges = customRanges.getTimeRangeList(); 
>    
>    if (timeRanges &amp;&amp; timeRanges.size() &gt; 0) 
>    { 
>    // CustomRangeResolver is only activated by the presence of CustomRanges in configuration 
>    resolvers.add(new CustomRangeResolver()); 
>    } 
>    } 
>    AdvertisingMetadata metadata = itemConfig.getAdvertisingMetadata(); 
>    if (metadata) { 
>    if (metadata instanceOf AuditudeSettings) 
>    resolvers.add(new AuditudeResolver(getContext()); 
>    } 
>    } 
>    // add your custom resolver if any 
>    resolvers.add(MyOpportunityGenerator(item)); 
>    return resolvers; 
>    } 
>    ... 
>   } 
>   
>   ```
>   
>   
>   
>1. Register the `codeph  ContentFactory` to the `codeph  MediaPlayer`.
>   For example:
>   ```java
>   //Register the custom content factory with the media player 
>   MediaPlayerItemConfig config = new MediaPlayerItemConfig(); 
>   config.setAdvertisingFactory(new MyContentFactory()); 
>    
>   //Pass this config while loading the resource 
>   mediaPlayer.replaceCurrentResource(resource, config); 
>    
>   // OR use MediaPlayerItemLoader to pre-load a resource 
>   id = 23; 
>   itemLoader.load(resource, id, config);
>   ```
>   
>   
>   
>1. Pass an `codeph  AdvertisingMetadata` object to  as follows:
>   >1. Create an `codeph  AdvertisingMetadata` object.
>   >   
>   >1. Save the `codeph  AdvertisingMetadata` object to `codeph  MediaPlayerItemConfig`.
>   >   ```java
>   >   AdvertisingMetadata advertisingMetadata = new AdvertisingMetadata(); 
>   >    
>   >   advertisingMetadata.setDelayAdLoading(true); 
>   >   ... 
>   >    
>   >   mediaPlayerItemConfig.setAdvertisingMetadata(advertisingMetadata); 
>   >   
>   >   ```
>   >   
>   >   
>   >   
>   
>1. Create a custom ad resolver class that extends the `codeph  ContentResolver` class.
>   >1. In the custom ad resolver, override `codeph  doConfigure`, `codeph  doCanResolve`, `codeph  doResolve`, `codeph  doCleanup`:
>   >   
>   >   ```java
>   >   void doConfigure(MediaPlayerItem item); 
>   >   boolean doCanResolve(Opportunity opportunity); 
>   >   void doResolve(Opportunity opportunity); 
>   >   void doCleanup();
>   >   ```
>   >   
>   >   You get your `codeph  advertisingMetadata` from the item passed in `codeph  doConfigure`:
>   >   ```java
>   >   MediaPlayerItemConfig itemConfig = item.getConfig(); 
>   >    
>   >   AdvertisingMetadata advertisingMetadata = 
>   >    mediaPlayerItemConfig.getAdvertisingMetadata(); 
>   >   
>   >   ```
>   >   
>   >   
>   >   
>   >1. For each placement opportunity, create a `codeph  List&lt;TimelineOperation&gt;`.
>   >   This sample `codeph  TimelineOperation` provides a structure for `codeph  AdBreakPlacement`:
>   >   ```java
>   >   AdBreakPlacement( 
>   >    new AdBreak( ads, // Vector&lt;Ad&gt; 
>   >    tracker // Content Tracker 
>   >    ), 
>   >    placementInformation // Retrieved from Opportunity 
>   >   ); 
>   >   
>   >   ```
>   >   
>   >   
>   >   
>   >1. After ads are resolved, call one of the following functions:
>   >* If the ad resolve succeeds, call `codeph  process(List&lt;TimelineOperation&gt; proposals)` and `codeph  notifyCompleted(Opportunity opportunity)` on the `codeph  ContentResolverClient`
>   >  
>   >  ```java
>   >  _client.process(timelineOperations); 
>   >  _client.notifyCompleted(opportunity); 
>   >  
>   >  ```
>   >  
>   >  
>   >* If the ad resolve fails, call `codeph  notifyResolveError` on the `codeph  ContentResolverClient`
>   >  
>   >  ```java
>   >  _client.notifyFailed(Opportunity opportunity, PSDKErrorCode error);
>   >  ```
>   >  
>   >  For example:
>   >  ```java
>   >  _client.notifyFailed(opportunity, UNSUPPORTED_OPERATION);
>   >  ```
>   >  
>   >  
>   >   
>   >   
>   >   
>   
>   
