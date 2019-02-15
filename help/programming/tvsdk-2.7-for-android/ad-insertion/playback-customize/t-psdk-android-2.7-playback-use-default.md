---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
uuid: 20785251-eb2f-4cc0-b919-1a88c0b1c57c
---

# Use the default playback behavior{#use-the-default-playback-behavior}

You can choose to use default ad behaviors.

1. To use default behaviors, complete one of the following tasks:

    * If you implement your own `AdvertisingFactory` class, return null for `createAdPolicySelector`. 
    
    * If you do not have a custom implementation for the `AdvertisingFactory` class, TVSDK uses a default ad policy selector.

