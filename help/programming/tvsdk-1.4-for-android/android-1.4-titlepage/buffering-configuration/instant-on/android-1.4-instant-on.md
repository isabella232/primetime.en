---
description: The term instant on refers to preloading one or more channels so that a user selecting a channel or switching channels sees content playing immediately. The buffering is already done by the time the user starts watching.
seo-description: The term instant on refers to preloading one or more channels so that a user selecting a channel or switching channels sees content playing immediately. The buffering is already done by the time the user starts watching.
seo-title: Instant on
title: Instant on
uuid: 4cb4d221-170f-46e8-af26-32f259377617
index: y
internal: n
snippet: y
---

# Instant on{#instant-on}

The term instant on refers to preloading one or more channels so that a user selecting a channel or switching channels sees content playing immediately. The buffering is already done by the time the user starts watching.

 Without instant on, TVSDK initializes the media to be played but does not start buffering the stream until the application calls `play`. The user sees no content until buffering is complete. With instant on, you can launch multiple media player (or media-player item loader) instances, and TVSDK starts buffering the streams immediately.

When a user changes the channel and the stream has buffered properly, calling `play` on the new channel starts playback immediately.

Although there are no limits to the number of `MediaPlayer` instances that TVSDK can run, running more instances consumes more resources. Application performance can be affected by the number of instances running. For more information about these instances, see  media-resource-load-using-mediaplayeritemloader . 
