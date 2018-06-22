---
description: You can implement your resolvers based on the default resolvers.
seo-description: You can implement your resolvers based on the default resolvers.
seo-title: Implement a custom opportunity/content resolver
title: Implement a custom opportunity/content resolver
---

# Implement a custom opportunity/content resolver



>1. Develop a custom ad resolver by extending the `codeph  PTContentResolver` abstract class.
>   `codeph  PTContentResolver` is an interface that must be implemented by a content resolver class. An abstract class with the same name is also available and handles the configuration automatically (getting the delegate).
>   >[!TIP]
>   >
>   >`codeph  PTContentResolver` is exposed through the `codeph  PTDefaultMediaPlayerClientFactory` class. Clients can register a new content resolver by extending the `codeph  PTContentResolver` abstract class. By default, and unless specifically removed, a `codeph  PTDefaultAdContentResolver` is registered in the `codeph  PTDefaultMediaPlayerClientFactory`.
>   
>       
>       ```
>       @protocol PTContentResolver &lt;NSObject&gt; 
>       @required 
>       + (BOOL)shouldHandleOpportunity:(PTPlacementOpportunity *)opportunity; 
>       //Detector returns YES/NO if it should handle the following placement opportunity 
>       - (void)configWithPlayerItem:(PTMediaPlayerItem *)item 
>        delegate:(id&lt;PTContentResolverDelegate&gt; delegate); 
>       - (void)process:(PTPlacementOpportunity *)opportunity; 
>       - (void)timeout:(PTPlacementOpportunity *)opportunity; 
>       //The timeout method gets invoked if the 
<ph conkeyref="phrases/primetime-sdk-name"></ph> decides that the 
>       //PTContentResolver is taking too much time to respond. 
>       @end 
>        
>       @interface PTContentResolver : NSObject &lt;PTContentResolver&gt; 
>        
>       @property (readonly) id&lt;PTContentResolverDelegate&gt; delegate; 
>       @property (readonly) PTMediaPlayerItem *playerItem; 
>        
>       - (BOOL)shouldHandleOpportunity:(PTPlacementOpportunity *)opportunity; 
>       - (void)configWithPlayerItem:(PTMediaPlayerItem *)item 
>        delegate:(id&lt;PTContentResolverDelegate&gt;) delegate; 
>       - (void)process:(NSArray *)opportunities; 
>       - (void)cancel:(NSArray *)opportunities; 
>       @end
>       ```
>       
>   
>1. Implement `codeph  shouldResolveOpportunity` and return `codeph  YES` if it should handle the received `codeph  PTPlacementOpportunity`.
>   
>1. Implement `codeph  resolvePlacementOpportunity`, which starts loading the alternate content or ads.
>   
>1. After the ads are loaded, prepare a `codeph  PTTimeline` with the information about the content to insert.
>   Here is some useful information about timelines:
>* There can be multiple `codeph  PTAdBreak`s of pre-roll, mid-roll, and post-roll types.
>    * A `codeph  PTAdBreak` has the following:
>        * A `codeph  CMTimeRange` with the start time and duration of the break.
>          This is set as the range property of `codeph  PTAdBreak`.
>          
>          
>        * `codeph  NSArray` of `codeph  PTAd`s.
>          This is set as the ads property of `codeph  PTAdBreak`.
>          
>          
>      
>  
>* A `codeph  PTAd` represents the ad, and each `codeph  PTAd` has the following:
>    * A `codeph  PTAdHLSAsset` set as the primary asset property of the ad.
>    * Possibly multiple `codeph  PTAdAsset` instances as clickable ads or banner ads.
>  
>   
>   
>       
>       ```
>       NSMutableArray *ptBreaks = [[[NSMutableArray alloc] init] autorelease]; 
>        
>       // Prepare the primary asset of the ad - links to ad m3u8 
>       PTAdHLSAsset *ptAdAsset = [[[PTAdHLSAsset alloc] init] autorelease]; 
>       ptAdAsset.source = AD_SOURCE_M3U8; 
>       ptAdAsset.id = FAKE_NUMBER_ID; 
>       ptAdAsset.format = @"video"; 
>        
>       // Prepare the ad itself. 
>       PTAd *ptAd = [[[PTAd alloc] init] autorelease]; 
>       ptAd.primaryAsset = ptAdAsset; 
>       ptAd.primaryAsset.ad = ptAd; 
>        
>       // Prepare the break and add the ad created above. 
>       PTAdBreak *ptBreak = [[[PTAdBreak alloc] init] autorelease]; 
>       ptBreak.relativeRange = CMTimeRangeMake(BREAK_START_TIME, BREAK_DURATION_VALUE); 
>       [ptBreak addAd:ptAd]; 
>        
>       // Add the break to array of breaks. 
>       [ptBreaks addObject:adBreak]; 
>        
>       // Once all breaks have been prepared, they can be set on timeline 
>       PTTimeline *_timeline = [[PTTimeline alloc] init]; 
>       _timeline.adBreaks = ptBreaks;
>       ```
>       
>   
>1. Call `codeph  didFinishResolvingPlacementOpportunity`, which provides the `codeph  PTTimeline`.
>   
>1. Register your custom content/ad resolver to the default media player factory by calling `codeph  registerContentResolver`.
>       
>       ```
>       //Remove default content/ad resolver 
>       [[PTDefaultMediaPlayerFactory defaultFactory] clearContentResolvers]; 
>        
>       //Create an instance of your content/ad resolver (id &lt;PTContentResolver&gt;) 
>       CustomContentResolver *contentResolver = [[CustomContentResolver alloc] init]; 
>        
>       //Set custom content/ad resolver 
>       [[PTDefaultMediaPlayerFactory defaultFactory] registerContentResolver:[contentResolver autorelease]];
>       ```
>       
>   
>1. If you implemented a custom opportunity resolver, register it to the default media player factory.
>   >[!TIP]
>   >
>   >You do not have to register a custom opportunity resolver to register a custom content/ad resolver.
>   
>       
>       ```
>       //Remove default opportunity resolver 
>       [[PTDefaultMediaPlayerFactory defaultFactory] clearOpportunityResolvers]; 
>        
>       //Create an instance of your opportunity resolver (id &lt;PTOpportunityResolver&gt;) 
>       CustomOpportunityResolver *opportunityResolver = [[CustomOpportunityResolver alloc] init]; 
>        
>       //Set custom opportunity resolver 
>       [[PTDefaultMediaPlayerFactory defaultFactory] 
>        registerOpportunityResolver:[opportunityResolver autorelease]];
>       ```
>       
>   
>   
