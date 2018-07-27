---
description: You can implement your own opportunity detectors by implementing the interface PlacementOpportunityDetector.
seo-description: You can implement your own opportunity detectors by implementing the interface PlacementOpportunityDetector.
seo-title: Implement a custom opportunity detector
title: Implement a custom opportunity detector
uuid: 6885f293-3900-4a63-85dd-395bfb94f086
index: n
internal: n
snippet: y
translate: y
---

# Implement a custom opportunity detector


>1. Create a custom ` AdvertisingFactory` instance and override ` createOpportunityDetector`. For example:

>    
>       ```
>       java>       new AdvertisingFactory() { 
>           ... 
>           @Override 
>           public PlacementOpportunityDetector createOpportunityDetector(MediaPlayerItem item) { 
>               return new CustomPlacementOpportunityDetector(); 
>           } 
>           ... 
>       }
>       ```
>1. Register the ad client factory to the ` MediaPlayer`. For example:

>    
>       ```
>       java>       // register the custom advertising factory with media player 
>       advertisingFactory = createCustomAdvertisingFactory(); 
>       mediaPlayer.registerAdClientFactory(advertisingFactory);
>       ```
>1. Create a custom opportunity detector class that extends the ` PlacementOpportunityDetector` class.
>   >1. In the custom opportunity detector, override this function:
>   >
>   >   ```
>   >   java>   >   public List&lt;PlacementOpportunity&gt; process(List&lt;TimedMetadata&gt; timedMetadataList, Metadata metadata)
>   >   ```
>   >   The ` timedMetadataList` contains the list of available ` TimedMetadata`, which is sorted. Metadata contains the targeting parameters and the custom parameters to be sent to the ad provider. 
>   >
>   >1. For each ` TimedMetadata`, create a ` List&lt;PlacementOpportunity&gt;`. The list can be empty, but not null. ` PlacementOpportunity` should have the following attributes:
>   >
>   >   ```
>   >   java>   >   PlacementOpportunity( 
>   >       String id,                                      // can be id from timedMetadata 
>   >       PlacementInformation placementInformation   // PlacementInformation object containing Type, time, duration 
>   >       Metadata metadata                           // ad metadata containing targeting params sent to the ad provider 
>   >   )
>   >   ```
>   >
>   >1. After placement opportunities are created for all the detected timed metadata objects, simply return the ` PlacementOpportunity` list.
