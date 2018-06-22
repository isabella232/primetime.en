---
description: You can override the default behavior for how handles seeks over ads when using custom ad markers.
seo-description: You can override the default behavior for how handles seeks over ads when using custom ad markers.
seo-title: Control playback behavior for seeking over custom ad markers
title: Control playback behavior for seeking over custom ad markers
---

# Control playback behavior for seeking over custom ad markers

By default, when a user seeks into or past ad sections that result from the placement of custom ad markers,  skips the ads. This might differ from the current playback behavior for standard ad breaks. You can set  to reposition the playhead to the beginning of the most recently skipped custom ad when the user seeks past one or more custom ads.

>1. Call `codeph  CustomRangeMetadata.setAdjustSeekPosition` with `codeph  true`.
>   ```java
>   customRangeMetadata.setAdjustSeekPosition (true);
>   ```
>   
>   
>1. Use `codeph  customRangeMetadata` in `codeph  MediaPlayerItemConfig`.
>   ```java
>   // Set customRangeMetadata 
>   config.setCustomRangeMetadata(customRangeMetadata); 
>    
>   // prepare the content for playback by calling replaceCurrentResource 
>   mediaPlayer.replaceCurrentResource(mediaResource, config); 
>   
>   ```
>   
>   
>   
