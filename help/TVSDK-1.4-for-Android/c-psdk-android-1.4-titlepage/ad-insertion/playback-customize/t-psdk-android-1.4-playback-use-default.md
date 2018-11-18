---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
uuid: bf63bf55-d637-40a8-8ba2-f90ff31adccf
index: y
internal: n
snippet: y
---

# Use the default playback behavior{#use-the-default-playback-behavior}

You can choose to use default ad behaviors.

1. To use default behaviors:

    * If you implement your own `AdvertisingFactory` class, return null for `createAdPolicySelector` . 
    
    * If you do not have a custom implementation for the `AdvertisingFactory` class, TVSDK uses  a default ad policy selector .

