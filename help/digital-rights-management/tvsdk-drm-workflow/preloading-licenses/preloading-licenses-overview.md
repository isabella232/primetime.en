---
seo-title: Pre-loading licenses for offline playback overview
title: Pre-loading licenses for offline playback overview
uuid: 588b6e20-66c6-4de0-8b8f-c9023f8423d5
index: y
internal: n
snippet: y
---

# Pre-loading licenses for offline playback overview{#pre-loading-licenses-for-offline-playback-overview}

You can preload the licenses required to play content protected by Primetime DRM. Pre-loaded licenses allow users to view the content whether or not they have an active Internet connection.

The preload process itself *does* require an Internet connection. You can use `DRMManager.loadVoucher()` ahead of time to preload licenses. Later, when the client wishes to play the desired content, the DRM system has been pre-primed and can play the protected content immediately. 
