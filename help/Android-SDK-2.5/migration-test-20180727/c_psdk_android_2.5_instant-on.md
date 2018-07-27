---
description: Enabling instant on means that one or more channels are preloaded. When users select a channel or switch channels, the content plays immediately. The buffering is complete by the time the user starts watching.
seo-description: Enabling instant on means that one or more channels are preloaded. When users select a channel or switch channels, the content plays immediately. The buffering is complete by the time the user starts watching.
seo-title: Instant On
title: Instant On
uuid: e65ac997-7dd4-43e9-b2d2-65108b9ca183
index: n
internal: n
snippet: y
translate: y
---

# Instant On

Without Instant On,  <!-- PH element: phrases/primetime-sdk-name --> initializes the media to be played but does not start buffering the stream until the application calls `play`. The user sees no content until buffering is complete. With Instant On, you can launch multiple media player (or media-player item loader) instances, and  <!-- PH element: phrases/primetime-sdk-name --> starts buffering the streams immediately. When a user changes the channel and the stream has buffered properly, calling `play` on the new channel starts playback immediately. 
Although there are no limits to the number of `MediaPlayer` and `MediaPlayerItemLoader` instances that  <!-- PH element: phrases/primetime-sdk-name --> can run, running more instances consumes more resources. Application performance can be affected by the number of instances that are running. For more information about `MediaPlayerItemLoader`, see [Load a media resource in the media player](t_psdk_android_2.5_media-resource-load.md#load-a-media-resource). 

>[!IMPORTANT]
>
><!-- PH element: phrases/primetime-sdk-name --> does not support a single `QoSProvider` to work with both `itemLoader` and `MediaPlayer`. If the customer uses Instant On, the application needs to maintain two QoS instances and manage both instances for the information. 

For more information about `MediaPlayerItemLoader`, see [Load a media resource using MediaPlayerItemLoader](t_psdk_android_2.5_media-resource-load-using-mediaplayeritemloader.md#use-mediaplayeritemloader).
