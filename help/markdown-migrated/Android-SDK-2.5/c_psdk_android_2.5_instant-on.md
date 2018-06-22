---
description: Enabling instant on means that one or more channels are preloaded. When users select a channel or switch channels, the content plays immediately. The buffering is complete by the time the user starts watching.
seo-description: Enabling instant on means that one or more channels are preloaded. When users select a channel or switch channels, the content plays immediately. The buffering is complete by the time the user starts watching.
seo-title: Instant On
title: Instant On
---

# Instant On

Without Instant On,  initializes the media to be played but does not start buffering the stream until the application calls `codeph play`. The user sees no content until buffering is complete. With Instant On, you can launch multiple media player (or media-player item loader) instances, and  starts buffering the streams immediately. When a user changes the channel and the stream has buffered properly, calling `codeph play` on the new channel starts playback immediately.

Although there are no limits to the number of `codeph MediaPlayer` and `codeph MediaPlayerItemLoader` instances that  can run, running more instances consumes more resources. Application performance can be affected by the number of instances that are running. For more information about `codeph MediaPlayerItemLoader`, see [Load a media resource in the media player](t_psdk_android_2.5_media-resource-load.md#load-a-media-resource).

>[!IMPORTANT]
>
>does not support a single`codeph QoSProvider` to work with both `codeph itemLoader` and `codeph MediaPlayer`. If the customer uses Instant On, the application needs to maintain two QoS instances and manage both instances for the information.
For more information about `codeph MediaPlayerItemLoader`, see [Load a media resource using MediaPlayerItemLoader](t_psdk_android_2.5_media-resource-load-using-mediaplayeritemloader.md#use-mediaplayeritemloader).

