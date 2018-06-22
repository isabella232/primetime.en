---
description: The PlayerFragment class is where you edit the code to create the fully-enabled feature managers.
seo-description: The PlayerFragment class is where you edit the code to create the fully-enabled feature managers.
seo-title: PlayerFragment
title: PlayerFragment
---

# PlayerFragment

The `codeph  PlayerFragment` class contains all the UI components such as the `codeph  playerFrame`, `codeph  ControlBar`, `codeph  playerClickableAdFragment`, and `codeph  adOverlay`.

It handles the initialization of all these components as well as creating the player, setting up the views, creating feature managers for the media player, handling media events such as resume, play, and pause and handling the event listeners for `codeph  QoSManager`, `codeph  DRMManager`, `codeph  CCManager`, `codeph  AAManager`, `codeph  AdsManager`, `codeph  PlaybackManager`, and `codeph  EntitlementManager`.

The XML file that includes the configuration parameters for the `codeph  PlayerFragment` is `filepath  res/layout/fragment_player.xml`.

Before you create the feature managers you need to create the media player by making sure the following code is in the `filepath  PlayerFragment.java` file:
```java
private MediaPlayer createMediaPlayer() { 
 MediaPlayer mediaPlayer = 
 DefaultMediaPlayer.create(getActivity().getApplicationContext()); 
 return mediaPlayer; 
}
```

