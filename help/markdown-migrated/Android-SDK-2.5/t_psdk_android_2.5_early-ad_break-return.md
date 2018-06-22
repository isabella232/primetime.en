---
description: For live stream ad insertion, you might need to exit from an ad break before all the ads in the break are played to completion.
seo-description: For live stream ad insertion, you might need to exit from an ad break before all the ads in the break are played to completion.
seo-title: Implement an early ad break return
title: Implement an early ad break return
---

# Implement an early ad break return

For example, the duration of the ad break in certain sports events might not be known before the break starts.  provides a default duration, but if the game resumes before the break finishes, the ad break must be exited. Another example is an emergency signal during an ad break in a live stream.

>1. Subscribe to `codeph  #EXT-X-CUE-OUT`, `codeph  #EXT-X-CUE-IN`, and `codeph  #EXT-X-CUE`, which are the splice out/splice in markers.
>   For more information about to how to splice out/in ad markers, see[]()
>   
>1. Use a custom `codeph  ContentFactory`.
>   
>1. In `codeph  retrieveGenerators`, use the `codeph  SpliceInPlacementOpportunityGenerator`.
>   For example:
>   ```java
>   public List&lt;OpportunityGenerator&gt; retrieveGenerators(MediaPlayerItem item) { 
>    List&lt;OpportunityGenerator&gt; generators = new ArrayList&lt;OpportunityGenerator&gt;(); 
>    generators.add(SpliceInPlacementOpportunityDetector(item)); 
>    return generators; 
>   }
>   ```
>   
>   For more information about using a custom `codeph  ContentFactory`, see step 1 in []().
>   
>   
>   
>1. On the same custom `codeph  ContentFactory`, implement `codeph  retrieveResolvers` and include `codeph  AuditudeResolver` and `codeph  SpliceInCustomResolver`.
>   For example:
>   ```java
>   List&lt;ContentResolver&gt; contentResolvers = new ArrayList&lt;ContentResolver&gt;(); 
>   contentResolvers.add(new AuditudeResolver(getActivity().getApplicationContext())); 
>   contentResolvers.add(new SpliceInCustomResolver()); 
>   return contentResolvers;
>   ```
>   
>   
>   
