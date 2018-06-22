---
description: Ad resolving and ad loading can cause an unacceptable delay for a user waiting for playback to start. The Lazy Ad Loading and Lazy Ad Resolving features can reduce this startup delay.
keywords: Lazy;Ad resolving;Ad loading
seo-description: Ad resolving and ad loading can cause an unacceptable delay for a user waiting for playback to start. The Lazy Ad Loading and Lazy Ad Resolving features can reduce this startup delay.
seo-title: Lazy ad resolving
title: Lazy ad resolving
---

# Lazy ad resolving


* Basic ad resolving and loading process:
    1. downloads a manifest (playlist) and *resolves* all of the ads.
    1. *loads* all of the ads and places them on the timeline.
    1. moves the player into the PREPARED status, and content playback begins.
  The player uses the URLs in the manifest to obtain the ad content (creatives), ensures that the ad content is in a format that  can play, and  places the ads on the timeline. This basic process of resolving and loading ads can cause an unacceptably long delay for a user waiting to play their content, especially if the manifest contains several ad URLs.
  
  
* *Lazy Ad Loading*:
    1. downloads a playlist and *resolves* all of the ads.
    1. *loads* pre-roll ads, moves the player into the PREPARED status, and content playback begins.
    1. *loads* the remaining ads and puts them on the timeline as playback occurs.
  This feature improves upon the basic process by putting the player into the PREPARED status before all ads are loaded.
  *
  *Lazy Ad Resolving*:
    1. downloads the playlist.
    1. resolves and loads any pre-roll ads, moves the player into the PREPARED status, and content playback begins.
    1. resolves and loads the remaining ads and puts them on the timeline as playback occurs.
  Lazy Ad Resolving builds on Lazy Ad Loading to allow for even faster start up. After places any pre-roll ads, it moves the player into the PREPARED status, and then resolves additional ads and places them on the timeline.
  
  

>[!IMPORTANT]
>
>Factors to consider with Lazy Ad Resolving:
>
>* Lazy Ad Resolving is enabled by default. If you disable it, all ads are resolved before playback starts.
>* Lazy Ad Resolving does not allow seeking or trickplay until after all the ads are resolved:
>    * The player must wait for the `codeph kEventAdResolutionComplete` event before allowing seeking or trick play.
>    * If the user attempts to perform seek or trick play operations while ads are still being resolved,  throws the `codeph kECLazyAdResolutionInProgress` error.
>    * If necessary, the player should update the scrub bar, *after* receiving the `codeph kEventAdResolutionComplete` event.
>  
>* Lazy Ad Resolving is for VOD only. It will not work with LIVE streams.
>* Lazy Ad Resolving is incompatible with the *Instant On* feature.
>  For more information about Instant On, see []().
>  
>  
>* While Lazy Ad Resolving results in playback starting much faster, if an ad break occurs in the first 60 seconds of playback, it may not get resolved.
>* Lazy ad resolution does not affect pre-roll ads.
>
>
