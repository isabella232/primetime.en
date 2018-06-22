---
description: By default, forces an ad break to play when the user seeks over an ad break. You can customize the behavior to skip an ad break if the time elapsed from a previous break completion is within a certain number of minutes.
seo-description: By default, forces an ad break to play when the user seeks over an ad break. You can customize the behavior to skip an ad break if the time elapsed from a previous break completion is within a certain number of minutes.
seo-title: Skip ad breaks for a period of time
title: Skip ad breaks for a period of time
---

# Skip ad breaks for a period of time

>[!IMPORTANT]
>
>If you have to complete an internal seek to forgive an ad, there might be a slight pause during the playback.
To override the default  ad break behavior, you can extend the default ad policy selector. There are four ad break policies available:

* PLAY
* SKIP
  >[!NOTE]
  >
  >The SKIP ad break policy might not work as expected for live streams when an ad is present at the live point. For example, for a pre-roll, SKIP will cause a seek to the end of the ad break, which could be greater than the live point. In this case, may seek to the middle of an ad.
  
* REMOVE_AFTER
* REMOVE
  >[!NOTE] {type="note"}
  >
  >The`codeph  REMOVE` ad break policy is slated for deprecation. Adobe recommends that you use the `codeph  SKIP` ad break policy in place of `codeph  REMOVE`.
  
The following example of a customized ad policy selector skips ads in the next five minutes (wall clock time) after a user has watched an ad break.

>1. When the user finishes watching an ad break, save the current system time.
>       
>       ```java
>       @Override 
>       public void onAdBreakComplete(AdBreak adBreak) { 
>        ... 
>        if (isShouldPlayUpcomingAdBreakRuleEnabled()) { 
>        CustomAdPolicySelector.setLastAdBreakPlayedTime(System.currentTimeMillis()); 
>        ... 
>        } 
>       }
>       ```
>       
>   
>1. Extend `codeph  AdPolicySelector`.
>       
>       ```java
>       package com.adobe.mediacore.sample.advertising; 
>        
>       import com.adobe.mediacore.MediaPlayerItem; 
>       import com.adobe.mediacore.MediaPlayerItemConfig; 
>       import com.adobe.mediacore.timeline.advertising.policy.*; 
>       import com.adobe.mediacore.timeline.advertising.AdBreakTimelineItem; 
>       import com.adobe.mediacore.metadata.AdvertisingMetadata; 
>        
>       import java.util.ArrayList; 
>       import java.util.List; 
>        
>       public class CustomAdPolicySelector implements AdPolicySelector { 
>        
>        private static final long MIN_BREAK_INTERVAL = 300000; // 5 minutes for next ad break to be played 
>        private MediaPlayerItem _mediaPlayerItem; 
>        private static long _lastAdBreakPlayedTime; 
>        private AdBreakWatchedPolicy watchedPolicy = AdBreakWatchedPolicy.WATCHED_ON_BEGIN; 
>        
>        public CustomAdPolicySelector(MediaPlayerItem mediaPlayerItem) { 
>        _mediaPlayerItem = mediaPlayerItem; 
>        _lastAdBreakPlayedTime = 0; 
>        
>        if (mediaPlayerItem != null) { 
>        watchedPolicy = extractWatchedPolicy(mediaPlayerItem.getConfig()); 
>        } 
>        } 
>        
>        @Override 
>        public AdBreakPolicy selectPolicyForAdBreak(AdPolicyInfo adPolicyInfo) { 
>        if (shouldPlayAdBreaks() &amp;&amp; adPolicyInfo.getAdBreakTimelineItems() != null) { 
>        
>        AdBreakTimelineItem item = adPolicyInfo.getAdBreakTimelineItems().get(0); 
>        
>        // This condition will remove the pre-roll ad from live stream after watching 
>        if (item.getTime() == 0 &amp;&amp; _mediaPlayerItem.isLive()) { 
>        return AdBreakPolicy.REMOVE_AFTER_PLAY; 
>        } 
>        if (item.getTime() == 0) { 
>        return AdBreakPolicy.PLAY; 
>        } 
>        
>        // This condition will remove every ad break that has been watched once. 
>        // Comment this section if you want to play watched ad breaks again. 
>        if (item.isWatched()) { 
>        return AdBreakPolicy.SKIP; 
>        } 
>        
>        return AdBreakPolicy.REMOVE_AFTER_PLAY; 
>        } 
>        
>        return AdBreakPolicy.SKIP; 
>        } 
>        
>        @Override 
>        public List&lt;AdBreakTimelineItem&gt; selectAdBreaksToPlay(AdPolicyInfo adPolicyInfo) { 
>        
>        if (shouldPlayAdBreaks()) { 
>        
>        List&lt;AdBreakTimelineItem&gt; timelineItems = adPolicyInfo.getAdBreakTimelineItems(); 
>        AdBreakTimelineItem item; 
>        List&lt;AdBreakTimelineItem&gt; selectedItems = new ArrayList&lt;AdBreakTimelineItem&gt;(); 
>        
>        if (timelineItems != null &amp;&amp; timelineItems.size() &gt; 0) { 
>        
>        // Seek Forward Condition 
>        if (adPolicyInfo.getCurrentTime() &lt;= adPolicyInfo.getSeekToTime()) { 
>        item = timelineItems.get(0); 
>        
>        // Resume logic - This will be helpful in resuming the content 
>        // from last saved playback session, and just play the pre-roll ad 
>        if(adPolicyInfo.getCurrentTime() == 0) { 
>        if(item.getTime() == 0 &amp;&amp; !item.isWatched()) { 
>        // comment this line if you just need to seek to the user's 
>        // last known position without playing pre-roll ad. ZD#820 
>        selectedItems.add(item); 
>        return selectedItems; 
>        } 
>        else{ 
>        return null; 
>        } 
>        } else { 
>        item = timelineItems.get(timelineItems.size()-1); 
>        if (!item.isWatched()) { 
>        selectedItems.add(item); 
>        return selectedItems; 
>        } 
>        } 
>        
>        // Seek backward condition 
>        } else if (adPolicyInfo.getCurrentTime() &gt; adPolicyInfo.getSeekToTime()) { 
>        item = timelineItems.get(0); 
>        
>        if(!item.isWatched()) { 
>        selectedItems.add(item); 
>        return selectedItems; 
>        } else { 
>        return null; 
>        } 
>        } 
>        } 
>        } 
>        return null; 
>        } 
>        
>        @Override 
>        public AdPolicy selectPolicyForSeekIntoAd(AdPolicyInfo adPolicyInfo) { 
>        // Simple Ad Policy selector 
>        // if the first ad in the break was watched, 
>        // skip to the next add after the seek position 
>        // otherwise, play the ads in the break from the beginning 
>        
>        List&lt;AdBreakTimelineItem&gt; timelineItems = adPolicyInfo.getAdBreakTimelineItems(); 
>        if (timelineItems != null &amp;&amp; timelineItems.size() &gt; 0) { 
>        if (timelineItems.get(0).isWatched()) { 
>        return AdPolicy.SKIP_TO_NEXT_AD_IN_AD_BREAK; 
>        } 
>        } 
>        
>        // Resume play from the next ad in the break 
>        return AdPolicy.PLAY_FROM_AD_BREAK_BEGIN; 
>        
>        } 
>        
>        @Override 
>        public AdBreakWatchedPolicy selectWatchedPolicyForAdBreak(AdPolicyInfo adPolicyInfo) { 
>        return watchedPolicy; 
>        } 
>        
>        public static void setLastAdBreakPlayedTime(long lastAdBreakPlayedTime) { 
>        _lastAdBreakPlayedTime = lastAdBreakPlayedTime; 
>        } 
>        
>        private boolean shouldPlayAdBreaks() { 
>        long currentTime = System.currentTimeMillis(); 
>        
>        if (_lastAdBreakPlayedTime &lt;= 0) { 
>        return true; 
>        } 
>        
>        if (_lastAdBreakPlayedTime &gt; 0 &amp;&amp; 
>        (currentTime - _lastAdBreakPlayedTime) &gt; MIN_BREAK_INTERVAL) { 
>        return true; 
>        } 
>        
>        // return false for not playing Ad if this 
>        // Ad occurs with 5 minutes of last Ad playback 
>        return false; 
>        } 
>        
>        private AdBreakWatchedPolicy extractWatchedPolicy(MediaPlayerItemConfig config) { 
>        if (config != null) { 
>        AdvertisingMetadata metadata = config.getAdvertisingMetadata(); 
>        if (metadata != null) { 
>        return metadata.getAdBreakWatchedPolicy(); 
>        } 
>        } 
>        return AdBreakWatchedPolicy.WATCHED_ON_BEGIN; 
>        } 
>       } 
>       
>       ```
>       
>   
>   
>   
