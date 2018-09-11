---
description: For live stream ad insertion, you might need to exit from an ad break before all the ads in the break are played to completion.
seo-description: For live stream ad insertion, you might need to exit from an ad break before all the ads in the break are played to completion.
seo-title: Implement an early ad break return
title: Implement an early ad break return
uuid: 30038fef-cfe2-46a1-995f-8fb448554f9f
index: y
internal: n
snippet: y
translate: y
---

# Implement an early ad break return

For live stream ad insertion, you might need to exit from an ad break before all the ads in the break are played to completion.


>Here are some examples for an early ad break return: >
>* The duration of the ad break in certain sports events. Although a default duration is provided, if the game resumes before the break finishes, the ad break must be exited. 
>
>* An emergency signal during an ad break in a live stream.>
>
>

>
>The ability to exit from an ad break early is identified through a custom tag in the manifest known as a splice-in or a cue-in tag. TVSDK allows the application to subscribe to these splice-in tags to provide a splice-in opportunity. 

<a id="section_AE9126531F974E11B3090A595F0444BA"></a>


* To use the `#EXT-X-CUE-IN` tag as a splice-in opportunity and implement an early ad break return: 
    1. Subscribe to the tag.     
       ```
       [PTSDKConfig setSubscribedTags:[NSArray arrayWithObject:@"#EXT-X-CUE-IN"]];
       ```

    
    1. Add the cue-in opportunity resolver.     
       ```
       // self.player is the PTMediaPlayer instance created for content and ad playback 
       PTDefaultMediaPlayerClientFactory *clientFactory = self.player.mediaPlayerClientFactory; 
             
       // Set cue in opportunity resolver 
       [clientFactory registerOpportunityResolver:[PTDefaultAdSpliceInOpportunityResolver adSpliceInOpportunityResolverWithTag:@"#EXT-X-CUE-IN"]];
       ```

    
    
    

* To share the same tag for splice-out and splice-in: 
    1. If the application is sharing the same cue to indicate cue-out/splice-out and cue-in/splice-in, extend `PTDefaultAdOpportunityResolver` and implement the `preparePlacementOpportunity` method. 
       >[!TIP]
       >
       >The following code assumes that the app has an implementation for the `isCueInOpportunity` method.        >
       >```
       >- (PTPlacementOpportunity *)preparePlacementOpportunity:(PTTimedMetadata *)timedMetadata 
       >{ 
       >    if ([self isCueInOpportunity:timedMetadata]) 
       >    { 
       >        return [PTPlacementOpportunity advertisementSpliceInOpportunityWithTimedMetadata:timedMetadata]; 
       >    } 
       >    else 
       >    { 
       >        return [super preparePlacementOpportunity:timedMetadata]; 
       >    } 
       >}
       >```


    
    1. Register the extended opportunity resolver on the `PTDefaultMediaPlayerClientFactory` instance.     
       ```
       // self.player is the PTMediaPlayer instance created for content and ad playback 
       PTDefaultMediaPlayerClientFactory *clientFactory = self.player.mediaPlayerClientFactory; 
             
       // Clear existing resolver and register the new opportunity resolver 
       [clientFactory clearOpportunityResolvers]; 
       [clientFactory registerOpportunityResolver:[[PTDefaultExtendedAdOpportunityResolver new] autorelease]];
       ```

    
    
    



