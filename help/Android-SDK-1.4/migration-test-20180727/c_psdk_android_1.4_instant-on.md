---
description: The term instant on refers to preloading one or more channels so that a user selecting a channel or switching channels sees content playing immediately. The buffering is already done by the time the user starts watching.
seo-description: The term instant on refers to preloading one or more channels so that a user selecting a channel or switching channels sees content playing immediately. The buffering is already done by the time the user starts watching.
seo-title: Instant on
title: Instant on
uuid: 8af63899-b152-48e6-afd6-57376f4f1086
index: n
internal: n
snippet: y
translate: y
---

# Instant on

Without instant on,  <!-- PH element: phrases/primetime-sdk-name --> initializes the media to be played but does not start buffering the stream until the application calls `play`. The user sees no content until buffering is complete. With instant on, you can launch multiple media player (or media-player item loader) instances, and  <!-- PH element: phrases/primetime-sdk-name --> starts buffering the streams immediately.
When a user changes the channel and the stream has buffered properly, calling `play` on the new channel starts playback immediately. 
Although there are no limits to the number of `MediaPlayer` instances that  <!-- PH element: phrases/primetime-sdk-name --> can run, running more instances consumes more resources. Application performance can be affected by the number of instances running. For more information about these instances, see media-resource-load-using-mediaplayeritemloader . 
