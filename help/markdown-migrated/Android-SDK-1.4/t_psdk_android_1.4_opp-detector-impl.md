---
description: You can implement your own opportunity detectors by implementing the interface PlacementOpportunityDetector.
seo-description: You can implement your own opportunity detectors by implementing the interface PlacementOpportunityDetector.
seo-title: Implement a custom opportunity detector
title: Implement a custom opportunity detector
---

# Implement a custom opportunity detector

>1. Create a custom `codeph  AdvertisingFactory` instance and override `codeph  createOpportunityDetector`. For example:
>       
>       ```java
>       new AdvertisingFactory() { 
>        ... 
>        @Override 
>        public PlacementOpportunityDetector createOpportunityDetector(MediaPlayerItem item) { 
>        return new CustomPlacementOpportunityDetector(); 
>        } 
>        ... 
>       }
>       ```
>       
>   
>1. Register the ad client factory to the `codeph  MediaPlayer`. For example:
>       
>       ```java
>       // register the custom advertising factory with media player 
>       advertisingFactory = createCustomAdvertisingFactory(); 
>       mediaPlayer.registerAdClientFactory(advertisingFactory);
>       ```
>       
>   
>1. Create a custom opportunity detector class that extends the `codeph  PlacementOpportunityDetector` class.
>   >1. In the custom opportunity detector, override this function:
>   >   ```java
>   >   public List&lt;PlacementOpportunity&gt; process(List&lt;TimedMetadata&gt; timedMetadataList, Metadata metadata)
>   >   ```
>   >   The `codeph  timedMetadataList` contains the list of available `codeph  TimedMetadata`, which is sorted. Metadata contains the targeting parameters and the custom parameters to be sent to the ad provider.
>   >   
>   >   
>   >   
>   >1. For each `codeph  TimedMetadata`, create a `codeph  List&lt;PlacementOpportunity&gt;`. The list can be empty, but not null. `codeph  PlacementOpportunity` should have the following attributes:
>   >   ```java
>   >   PlacementOpportunity( 
>   >    String id, // can be id from timedMetadata 
>   >    PlacementInformation placementInformation // PlacementInformation object containing Type, time, duration 
>   >    Metadata metadata // ad metadata containing targeting params sent to the ad provider 
>   >   )
>   >   ```
>   >   
>   >   
>   >1. After placement opportunities are created for all the detected timed metadata objects, simply return the `codeph  PlacementOpportunity` list.
>   >   
>   >   
>   
>   
