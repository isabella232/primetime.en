---
description: You can enable or disable the Lazy Ad Resolving feature, currently a beta feature and only available on 1.5 builds of for iOS, using the existing Lazy Ad Loading mechanism. Lazy Ad Resolving is disabled by default on iOS.
keywords: Lazy;Ad resolving;Ad loading
seo-description: You can enable or disable the Lazy Ad Resolving feature, currently a beta feature and only available on 1.5 builds of for iOS, using the existing Lazy Ad Loading mechanism. Lazy Ad Resolving is disabled by default on iOS.
seo-title: Enable lazy ad resolving
title: Enable lazy ad resolving
---

# Enable lazy ad resolving

You can enable or disable Lazy Ad Resolving by setting the `codeph  delayAdLoading` property on calling `codeph  [ PTAuditudeMetadata ](http://help.adobe.com/en_US/primetime/api/psdk/appledoc/Classes/PTAuditudeMetadata.html)` to `codeph  YES` or `codeph  NO`. The default is NO. This property must be set prior to initializing the playback.

>[!TIP]
>
>The property is only available on 1.5 builds of for iOS.
>1. Set the Boolean `codeph  delayAdLoading` property in `codeph  PTAuditudeMetadata` <!-- to control the timing of ad resolution and the placement of ads on the timeline: -->
>* If `codeph  delayAdLoading` is `codeph  NO`,  waits until all ads are resolved and placed on the timeline before transitioning to the READY state.
>* If `codeph  delayAdLoading` is `codeph  YES`,  resolves only the pre-roll ads and transitions to the READY state. The remaining ads are resolved and placed on the timeline during playback at or before the expected playback time of an ad break.
>   APIs relevant to lazy ad resolution:
>   
>   ```
>   Class: 
>    PTAuditudeMetadata 
>    
>   Property: 
>    @property (non atomic, assign) BOOL delayAdLoading; 
>   
>   ```
>   
>   
>1. To accurately reflect ads as cues on a scrub bar, listen for the `codeph  PTMediaPlayerTimelineChangedNotification` notification and redraw the scrub bar every time that you receive this notification.
>   When Lazy Ad Resolving is enabled for VOD streams, not all ads are placed on the timeline when your player enters the READY state, so your player must explicitly redraw the scrub bar.
>   
>   
>   
>   
