---
description: You can enable or disable the Lazy Ad Resolving feature using the existing Lazy Ad Loading mechanism (Lazy Ad Resolving is enabled by default).
keywords: Lazy;Ad resolving;Ad loading;delayLoading
seo-description: You can enable or disable the Lazy Ad Resolving feature using the existing Lazy Ad Loading mechanism (Lazy Ad Resolving is enabled by default).
seo-title: Enable lazy ad resolving
title: Enable lazy ad resolving
---

# Enable lazy ad resolving

You can enable or disable Lazy Ad Resolving by calling `codeph  [ AdvertisingMetadata.setDelayLoading ](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_2.4/com/adobe/mediacore/metadata/AdvertisingMetadata.html#setDelayAdLoading-boolean-)` with `codeph  true` or `codeph  false`.

>1. Use the Boolean `codeph  hasDelayAdLoading` and `codeph  setDelayAdLoading` methods in `codeph  AdvertisingMetadata` to control the timing of ad resolution and the placement of ads on the timeline:
>* If `codeph  hasDelayAdLoading` returns false,  waits until all ads are resolved and placed before transitioning to the PREPARED state.
>* If `codeph  hasDelayAdLoading` returns true,  resolves only the initial ads and transitions to the PREPARED state. The remaining ads are resolved and placed during playback.
>* When `codeph  hasPreroll` or `codeph  hasLivePreroll` return false,  assumes that there is no preroll ad and starts the playback of the content immediately. These default to true.
>   APIs relevant to lazy ad resolution:
>   ```
>   Class: 
>    com.adobe.mediacore.metadata.AdvertisingMetadata 
>    
>   Methods: 
>   […] 
>    public final boolean hasDelayAdLoading() // Check if Lazy Ad Resolving enabled 
>    public final void setDelayAdLoading() // Enable or disable Lazy Ad Resolving 
>    public final boolean hasPreroll() // Check for existence of pre-roll ads 
>    public final void setPreroll() // Set pre-roll true or false 
>    public final boolean hasLivePreroll() // Check for live pre-roll ads 
>    public final void setLivePreroll() // Set live pre-roll true or false 
>   […]
>   ```
>   
>   
>   
>   
>   
>1. To accurately reflect ads as cues on a scrub bar, listen for the `codeph  TimelineEvent` event and redraw the scrub bar every time that you receive this event.
>   When Lazy Ad Resolving is enabled for VOD streams, not all ads are placed on the timeline when your player enters the PREPARED state, so your player must explicitly redraw the scrub bar.
>   
>   optimizes the dispatch of this event to minimize the number of times that you must redraw the scrub bar; therefore, the number of timeline events is not related to the number of ad breaks to be placed on the timeline. For example, if you have five ad breaks, you might not receive exactly five events.
>   
>   
>       
>       ```java
>       mediaPlayer.addEventListener 
>        (MediaPlayerEvent.TIMELINE_UPDATED, timelineUpdatedEventListener); 
>       /** 
>        * ... 
>        */ 
>       public void onTimelineUpdated(TimelineEvent event) { 
>        
>        for (PlaybackManagerEventListener listener : eventListeners) { 
>        listener.onUpdate(getLocalSeekRange(), event.getTimeline()); 
>        } 
>       } 
>       
>       ```
>       
>   
>   
