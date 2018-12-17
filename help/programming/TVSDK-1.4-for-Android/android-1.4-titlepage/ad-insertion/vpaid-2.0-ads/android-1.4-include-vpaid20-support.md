---
description: To add VPAID 2.0 support, add a custom ad view and appropriate listeners.
seo-description: To add VPAID 2.0 support, add a custom ad view and appropriate listeners.
seo-title: Implement VPAID 2.0 integration
title: Implement VPAID 2.0 integration
uuid: ad16f4d5-5cce-4f6d-ad8c-8cf7c839fba6
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

