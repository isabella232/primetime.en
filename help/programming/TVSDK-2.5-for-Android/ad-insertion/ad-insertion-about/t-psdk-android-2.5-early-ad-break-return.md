---
description: For live stream ad insertion, you might need to exit from an ad break before all the ads in the break are played to completion.
seo-description: For live stream ad insertion, you might need to exit from an ad break before all the ads in the break are played to completion.
seo-title: Implement an early ad break return
title: Implement an early ad break return
uuid: 5116b6f2-de65-4fc3-8f27-99b40c7b693a
index: y
internal: n
snippet: y
---

# Implement an early ad break return{#implement-an-early-ad-break-return}

For live stream ad insertion, you might need to exit from an ad break before all the ads in the break are played to completion.

For example, the duration of the ad break in certain sports events might not be known before the break starts. TVSDK provides a default duration, but if the game resumes before the break finishes, the ad break must be exited. Another example is an emergency signal during an ad break in a live stream. 

1. Subscribe to `#EXT-X-CUE-OUT`, `#EXT-X-CUE-IN`, and `#EXT-X-CUE`, which are the splice out/splice in markers.

   For more information about to how to splice out/in ad markers, see  content-resolver-about  
1. Use a custom `ContentFactory`.
1. In `retrieveGenerators`, use the `SpliceInPlacementOpportunityGenerator`.

   For example: 

   ```java
   public List<OpportunityGenerator> retrieveGenerators(MediaPlayerItem item) { 
       List<OpportunityGenerator> generators = new ArrayList<OpportunityGenerator>(); 
       generators.add(SpliceInPlacementOpportunityDetector(item)); 
       return generators; 
   }
   ```

   For more information about using a custom `ContentFactory`, see step 1 in  opp-detector-impl . 

1. On the same custom `ContentFactory`, implement `retrieveResolvers` and include `AuditudeResolver` and `SpliceInCustomResolver`.

   For example: 

   ```java
   List<ContentResolver> contentResolvers = new ArrayList<ContentResolver>(); 
   contentResolvers.add(new AuditudeResolver(getActivity().getApplicationContext())); 
   contentResolvers.add(new SpliceInCustomResolver()); 
   return contentResolvers;
   ```

