---
description: Instantiate a MediaPlayer and place a view of it into a frame layout.
seo-description: Instantiate a MediaPlayer and place a view of it into a frame layout.
seo-title: Set up the MediaPlayer
title: Set up the MediaPlayer
uuid: 650e9371-75b0-4d66-8bab-eb84acff98ec
index: y
internal: n
snippet: y
translate: y
---

# Set up the MediaPlayer

Instantiate a MediaPlayer and place a view of it into a frame layout.


1. Instantiate `MediaPlayer`, passing an `android.content.Context` object to the constructor:

   ```
   java   MediaPlayer mediaPlayer = new MediaPlayer(context);
   ```

1. Provide a frame layout ( `android.widget.FrameLayout`) to hold a `ViewGroup` of `mediaPlayer`:



   ```
   java   FrameLayout playerFrame = (FrameLayout) _viewGroup.findViewById(R.id.playerFrame);
   ```


   Below is the code snippet to create `_viewGroup`. 

   ```
   @Override 
    public ViewGroup onCreateView(LayoutInflater inflater, ViewGroup container, 
      Bundle savedInstanceState) { 
     _viewGroup = (ViewGroup) inflater.inflate( 
       R.layout.fragment_player, container, false); 
     return _viewGroup; 
    }
   ```

1. Place a view of `mediaPlayer` inside the frame layout:

   ```
   java   playerFrame.addView(mediaPlayer.getView());
   ```

>The `MediaPlayer` instance ( `mediaPlayer`) is now available and properly configured to display video content on the device screen. 
