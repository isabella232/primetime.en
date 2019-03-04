---
description: You can choose to use default ad behaviors.
seo-description: You can choose to use default ad behaviors.
seo-title: Use the default playback behavior
title: Use the default playback behavior
uuid: ccda5223-17c1-4cda-b875-e706f5dc8648
---

# Use the default playback behavior {#use-the-default-playback-behavior}

You can choose to use default ad behaviors.

   To use default behaviors:

    * If you implement your own `AdvertisingFactory` class, return null for `createAdPolicySelector` . 
    
    * If you do not have a custom implementation for the `AdvertisingFactory` class, TVSDK uses  a default ad policy selector .