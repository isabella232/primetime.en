---
description: When users fast forward or fast rewind through the media, they are in the trick play mode. To enter trick play mode, you need to set the MediaPlayer playback rate to a value other than 1.
seo-description: When users fast forward or fast rewind through the media, they are in the trick play mode. To enter trick play mode, you need to set the MediaPlayer playback rate to a value other than 1.
seo-title: Implement fast forward and rewind
title: Implement fast forward and rewind
uuid: ebe7d9dd-39e4-4ebd-8f3d-0ab096a9d134
index: n
internal: n
snippet: y
translate: y
---

# Implement fast forward and rewind

To switch the speed, you must set one value.

>1. Move from normal play mode (1x) to trick play mode by setting the ` rate` property on the ` MediaPlayer` to an allowed value.
>    
>    * The ` MediaPlayerItem` class defines the allowed playback rates.
>    * <!-- PH element: phrases/primetime-sdk-name --> selects the closest allowed rate if the specified rate is not allowed.
>       When the trickplay rate is changed from 0 (pause) or 1 (normal play) to a rate that is greater than 1 or less than -1, all the ads on the timeline are removed. There is only one period on the entire timeline that facilitates a trickplay action to allow the content to be fast forwarded and rewound without stopping at any ad position. This action is enabled by a timeline detachment action on  <!-- PH element: phrases/primetime-sdk-name --> to remove all the resolved adBreaks. When trickplay resumes at 0 or 1, the adBreaks are first restored by the timeline attachment action.
>       Remember the following information: >    
>    * If the trickplay action is to rewind the content, the playback resumes when rate is changed to 1.
>    * If the trickplay action is to fast forward the content, the last skipped adBreak plays at the resume position.

>    

>       This example sets the player's internal playback rate to the requested rate.

>    
>       ```
>       private function onPlaybackRateChange(event:IndexChangeEvent):void { 
>           var newRateIndex:int = event.newIndex; 
>           var newRate:Number = _playbackRates[newRateIndex]; 
>        
>           _player.rate = newRate; 
>       } 
>       
>       ```
>1. You can optionally listen for rate-change events, which let you know when you requested a rate change and when a rate change actually happens.
>       <!-- PH element: phrases/primetime-sdk-name --> dispatches the following events related to trick play:>    
>    * ` mediacore.events.PlaybackRateEvent.RATE_SELECTED` when the ` rate` value changes to a different value.
>    * ` mediacore.events.PlaybackRateEvent.RATE_PLAYING` when playback resumes at the selected rate.
>       <!-- PH element: phrases/primetime-sdk-name --> dispatches both of these events when the player returns from trick-play mode to normal play mode.
>    
