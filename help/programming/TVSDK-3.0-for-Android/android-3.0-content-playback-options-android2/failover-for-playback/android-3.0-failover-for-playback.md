---
description: Streaming over the Internet requires a constant and stable connection to play a stream from a remote server. However, the variability of a viewer's Internet connection or streaming playback means that remote playback might not have the quality of media that is played locally.
seo-description: Streaming over the Internet requires a constant and stable connection to play a stream from a remote server. However, the variability of a viewer's Internet connection or streaming playback means that remote playback might not have the quality of media that is played locally.
seo-title: Playback and failover
title: Playback and failover
uuid: e6cd25b6-5659-4602-aa76-18f55683b5c9
index: y
internal: n
snippet: y
---

# Playback and failover{#playback-and-failover}

Streaming over the Internet requires a constant and stable connection to play a stream from a remote server. However, the variability of a viewer's Internet connection or streaming playback means that remote playback might not have the quality of media that is played locally.

>[!IMPORTANT]
>
>Primetime cannot protect from failures such as an ISP outage or a cable disconnection.

Primetime streaming provides failover protection to protect playback from certain remote server failures or operational failures, which makes a better viewing experience. Despite transmission problems, TVSDK implements failover protection to minimize playback interruptions and achieve a seamless playback. The video player automatically switches to a backup media set when entire renditions or fragments are unavailable. 
