---
description: You can implement your own content resolvers based on the default resolvers.
seo-description: You can implement your own content resolvers based on the default resolvers.
seo-title: Implement a custom content resolver
title: Implement a custom content resolver
---

# Implement a custom content resolver

When  detects a new opportunity, it iterates through the registered content resolvers looking for one that is capable of resolving that opportunity. The first one that returns true is selected for resolving the opportunity. If no content resolver is capable, then that opportunity is skipped. Because the content resolving process is usually asynchronous, the content resolver is responsible for notifying  when the process has completed.



>1. Create a custom `codeph  AdvertisingFactory` instance and override `codeph  createContentResolver`.
>   For example:
>       
>       ```java
>       new AdvertisingFactory() { 
>        ... 
>        @Override 
>        public ContentResolver createContentResolver(MediaPlayerItem item) { 
>        Metadata metadata = _mediaPlayer.getCurrentItem().getResource().getMetadata(); 
>        if (metadata != null) { 
>        if (metadata.containsKey(DefaultMetadataKeys.AUDITUDE_METADATA_KEY.getValue())) { 
>        return new AuditudeResolver(getActivity().getApplicationContext()); 
>        } else if (metadata.containsKey(DefaultMetadataKeys.JSON_METADATA_KEY.getValue())) { 
>        return new MetadataResolver(); 
>        } else if (metadata.containsKey(DefaultMetadataKeys.TIME_RANGES_METADATA_KEY.getValue())) { 
>        return new CustomAdMarkersContentResolver(); 
>        } else if (metadata.containsKey(CustomAdResolver.CUSTOM_METADATA_KEY)) { 
>        return new CustomAdResolver(); 
>        } 
>        } 
>        return null; 
>        } 
>        ... 
>       }
>       ```
>       
>   
>1. Register the ad client factory to the `codeph  MediaPlayer`.
>   For example:
>       
>       ```java
>       // register the custom advertising factory with media player 
>       advertisingFactory = createCustomAdvertisingFactory(); 
>       mediaPlayer.registerAdClientFactory(advertisingFactory);
>       ```
>       
>   
>1. Pass an `codeph  AdvertisingMetadata` object to  as follows:
>   >1. Create an `codeph  AdvertisingMetadata` object and `codeph  MetadataNode` object.
>   >   
>   >1. Save the `codeph  AdvertisingMetadata` object to `codeph  MetadataNode`.
>   >   
>   >   
>       
>       ```java
>       MetadataNode result = new MetadataNode(); 
>       result.setNode(DefaultMetadataKeys.ADVERTISING_METADATA.getValue(), 
>        advertisingMetadata);
>       ```
>       
>   
>1. Create a custom ad resolver class that extends the `codeph  ContentResolver` class.
>   >1. In the custom ad resolver, override this protected function:
>   >   ```java
>   >   void doResolveAds(Metadata metadata, 
>   >    PlacementOpportunity placementOpportunity)
>   >   ```
>   >   Metadata contains your `codeph  AdvertisingMetada`. Use it for the following `codeph  TimelineOperation` vector generation.
>   >   
>   >   
>   >   
>   >1. For each placement opportunity, create a `codeph  Vector&lt;TimelineOperation&gt;`.
>   >   The vector can be empty, but not null.
>   >       
>   >       `codeph  TimelineOperation`
>   >       `codeph  AdBreakPlacement`
>   >       ```java
>   >       AdBreakPlacement(AdBreak.createAdBreak( 
>   >        ads, // Vector&lt;Ad&gt; 
>   >        time, // Ad Break start time. Note: local time on the timeline 
>   >        duration, // Ad Break duration 
>   >        tag() // An arbitrary string value that can be attached to 
>   >        // the AdBreak object. 
>   >        ), placementInformation // Retrieved from PlacementOpportunity 
>   >       )
>   >       ```
>   >       
>   >   
>   >1. After ads are resolved, call one of the following functions:
>   >* If the ad resolve succeeds: `codeph  notifyResolveComplete(Vector&lt;TimelineOperation&gt; proposals)`
>   >* If the ad resolve fails: `codeph  notifyResolveError(Error error)`
>   >   
>   >       
>   >       ```java
>   >       Metadata metadata = new MetadataNode(); 
>   >       metadata.setValue("NATIVE_ERROR_CODE", exception.getCause().toString()); 
>   >       error.setMetadata(metadata);
>   >       ```
>   >       
>   >   
>   >   
>   
>   
