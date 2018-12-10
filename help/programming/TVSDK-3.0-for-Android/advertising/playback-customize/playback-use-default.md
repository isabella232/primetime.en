---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
uuid: 6d20a036-06dc-4c71-a196-a29ab859ef82
index: y
internal: n
snippet: y
---

# Use the default playback behavior{#use-the-default-playback-behavior}

You can choose to use default ad behaviors.

1. To use default behaviors, complete one of the following tasks:

    * If you implement your own `AdvertisingFactory` class, return null for `createAdPolicySelector`. 
    
    * If you do not have a custom implementation for the `AdvertisingFactory` class, TVSDK uses a default ad policy selector.

