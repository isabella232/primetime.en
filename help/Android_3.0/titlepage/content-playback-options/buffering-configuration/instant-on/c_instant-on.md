---
description: Enabling instant on means that one or more channels are preloaded. When users select a channel or switch channels, the content plays immediately. The buffering is complete by the time the user starts watching.
seo-description: Enabling instant on means that one or more channels are preloaded. When users select a channel or switch channels, the content plays immediately. The buffering is complete by the time the user starts watching.
seo-title: Instant On
title: Instant On
uuid: f98c97c4-5d59-4c3d-b345-3c695614e838
index: y
internal: n
snippet: y
translate: y
---

# Instant On

Enabling instant on means that one or more channels are preloaded. When users select a channel or switch channels, the content plays immediately. The buffering is complete by the time the user starts watching.

Without Instant On, TVSDK initializes the media to be played but does not start buffering the stream until the application calls `play`. The user sees no content until buffering is complete. With Instant On, you can launch multiple media player (or media-player item loader) instances, and TVSDK starts buffering the streams immediately. When a user changes the channel and the stream has buffered properly, calling `play` on the new channel starts playback immediately. 

Although there are no limits to the number of `MediaPlayer` and `MediaPlayerItemLoader` instances that TVSDK can run, running more instances consumes more resources. Application performance can be affected by the number of instances that are running. For more information about `MediaPlayerItemLoader`, see [Load a media resource in the media player](../../../../titlepage/content-playback-options/mediaplayer-initialize-for-video/t_media-resource-load.md#load-a-media-resource). 

>[!IMPORTANT]
>
>TVSDK does not support a single `QoSProvider` to work with both `itemLoader` and `MediaPlayer`. If the customer uses Instant On, the application needs to maintain two QoS instances and manage both instances for the information. 
For more information about `MediaPlayerItemLoader`, see [Load a media resource using MediaPlayerItemLoader](../../../../titlepage/content-playback-options/mediaplayer-initialize-for-video/t_media-resource-load-using-mediaplayeritemloader.md#use-mediaplayeritemloader). 
