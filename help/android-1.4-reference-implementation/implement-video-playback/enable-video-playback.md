---
description: Create a PlaybackManager that handles the HLS stream setup and playback operation. No other configuration is required.
seo-description: Create a PlaybackManager that handles the HLS stream setup and playback operation. No other configuration is required.
seo-title: Enable video playback
title: Enable video playback
uuid: ddc0defa-c40f-4ee6-a69f-d5eeca6c2fce
---

# Enable video playback{#enable-video-playback}

Create a PlaybackManager that handles the HLS stream setup and playback operation. No other configuration is required.

1. Create the media player object by making sure the following code exists in [!DNL PlayerFragment.java]:

   ```java
   private MediaPlayer createMediaPlayer() { 
           MediaPlayer mediaPlayer = DefaultMediaPlayer.create(getActivity().getApplicationContext()); 
           return mediaPlayer;
   ```

   <!-- I've duplicated this information. It also exists in the PlayerFragment section, just before the Feature manager section. I figured that I should have it here as well, in case they jump directly to this section.-->

1. Create the playback manager through the `ManagerFactory`:

   ```java
   playbackManager = ManagerFactory.getPlaybackManager(config, mediaPlayer);
   ```

1. Implement the `PlaybackManagerEventListener` in the `PlayerFragment` to handle the playback events:

   ```java
   private final PlaybackManagerEventListener playbackManagerEventListener =  
     new PlaybackManagerEventListener() 
   ```

1. Register the event listener in the `PlayerFragment`:

   ```
   playbackManager.addEventListener(playbackManagerEventListener);
   ```

1. Set up the video resource:

   ```
   playbackManager.setupVideo(url, adsManager); 
   ```

1. Set up the control bar operations in the `PlayerFragment`:

   ```
   controlBar.pressPlay() { 
       playbackManager.play();  
   }
   ```

1. [Class PlaybackManager](https://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/manager/PlaybackManager.html)
1. [PlaybackManagerEventListener](https://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/manager/PlaybackManager.PlaybackManagerEventListener.html)
1. [mediacore.utils.TimeRange](https://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/utils/TimeRange.html)
1. [mediacore.BufferControlParameters](https://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/BufferControlParameters.html)
1. [mediacore.MediaPlayer.PlayerState](https://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/MediaPlayer.PlayerState.html)
