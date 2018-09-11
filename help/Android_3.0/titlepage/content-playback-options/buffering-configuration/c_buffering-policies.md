---
description: Depending on your environment (including the device, the operating system, or the network conditions), you can set different buffering policies for your player, such as changing the minimum duration for initial buffering and for ongoing playback buffering.
seo-description: Depending on your environment (including the device, the operating system, or the network conditions), you can set different buffering policies for your player, such as changing the minimum duration for initial buffering and for ongoing playback buffering.
seo-title: Buffering time policies
title: Buffering time policies
uuid: 59d3ee3f-041b-405a-a3a9-e1673acef226
index: y
internal: n
snippet: y
translate: y
---

# Buffering time policies

Depending on your environment (including the device, the operating system, or the network conditions), you can set different buffering policies for your player, such as changing the minimum duration for initial buffering and for ongoing playback buffering.

After you call `play`, the media player begins buffering the video. When the media player has buffered the amount of video specified by the initial buffer time, playback begins. This process improves the start-up time because the player does not wait for the entire playback buffer to fill before starting playback. Instead, after the few initial seconds are buffered, playback begins. 

While the video is being rendered, TVSDK continues to buffer new fragments until it is has buffered the amount that is specified by the playback buffer time. If the current buffer length drops below the playback buffer time, the player will download additional fragments. Once the current buffer length is above the playback buffer time by a few seconds, TVSDK will stop downloading fragments. 

>[!TIP]
>
>If the initial buffer value is high, it might give your user a long initial buffering time before starting. That might provide smooth playback for a longer time; however, if network conditions are poor, initial playback could be delayed.
If you enable instant on by calling `prepareBuffer`, the initial buffering begins at that moment, instead of waiting for `play`. 
