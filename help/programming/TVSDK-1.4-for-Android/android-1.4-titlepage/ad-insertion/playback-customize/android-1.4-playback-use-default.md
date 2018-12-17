---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
uuid: 887a937a-7758-44d2-a799-98c7167a0735
index: y
internal: n
snippet: y
---

# Use the default playback behavior{#use-the-default-playback-behavior}

You can choose to use default ad behaviors.

1. To use default behaviors:

    * If you implement your own `AdvertisingFactory` class, return null for `createAdPolicySelector` . 
    
    * If you do not have a custom implementation for the `AdvertisingFactory` class, TVSDK uses  a default ad policy selector .

