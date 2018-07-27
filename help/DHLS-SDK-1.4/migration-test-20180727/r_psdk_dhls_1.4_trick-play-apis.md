---
description: includes methods, properties, and events to determine valid rates, current rates, whether trick play is supported, and other functionality related to fast forward and rewind.
seo-description: includes methods, properties, and events to determine valid rates, current rates, whether trick play is supported, and other functionality related to fast forward and rewind.
seo-title: Rate-change API elements
title: Rate-change API elements
uuid: 824ad340-4baa-4890-b150-315433e3d871
index: n
internal: n
snippet: y
translate: y
---

# Rate-change API elements


<a id="section_36576E92DE6343AEBD0BBD662502365D"></a>

Use the following API elements to change play rates:
* ` MediaPlayer.rate` property with setter and getter functions
* ` MediaPlayer.localTime property` with getter function
* ` mediacore.events.PlaybackRateEvent.RATE_SELECTED`
* ` mediacore.events.PlaybackRateEvent.RATE_PLAYING`
* ` MediaPlayerItem.IsTrickPlaySupported` property with getter function
* ` AdBreakPlaybackEvent.AD_BREAK_SKIPPED`
* ` MediaPlayerItem.availablePlaybackRates` property with getter function - specifies valid rates.


|  Rate value  | Effect on playback  |
|---|---|
|  2.0, 4.0, 8.0, 16.0, 32.0, 64.0   | Switches to fast-forward mode with the specified multiplier faster than normal (for example, 4 is 4 times faster than normal)  |
|  -2.0, -4.0, -8.0, -16.0, -32.0, -64.0   | Switches to fast-rewind mode  |
|  1.0  | Switches to normal play mode (calling ` play` is the same as setting the rate property to 1.0)  |
|  0.0  | Pauses (calling ` pause` is the same as setting the rate property to 0.0)  |

