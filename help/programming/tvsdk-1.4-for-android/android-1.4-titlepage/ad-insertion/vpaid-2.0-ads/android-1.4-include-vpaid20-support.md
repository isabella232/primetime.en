---
description: To add VPAID 2.0 support, add a custom ad view and appropriate listeners.
seo-description: To add VPAID 2.0 support, add a custom ad view and appropriate listeners.
seo-title: Implement VPAID 2.0 integration
title: Implement VPAID 2.0 integration
uuid: 7d11ffd8-240c-4a95-94e6-ff4417c8942e
index: y
internal: n
snippet: y
---

# Implement VPAID 2.0 integration{#implement-vpaid-integration}

To add VPAID 2.0 support, add a custom ad view and appropriate listeners.

To add VPAID 2.0 support: 

1. Add the custom ad view to the player interface.

   ```java
   _playerFrame.addView(mediaPlayer.createCustomAdView());
   ```

1. Add a listener for custom ad events.

   ```java
   mediaplayer.addEventListener(MediaPlayer.Event.CUSTOM_AD,  
     _customAdEventListener);
   ```

