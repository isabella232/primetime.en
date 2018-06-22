---
description: Instantiate a MediaPlayer and place a view of it into a frame layout.
seo-description: Instantiate a MediaPlayer and place a view of it into a frame layout.
seo-title: Set up the MediaPlayer
title: Set up the MediaPlayer
---

# Set up the MediaPlayer

>1. Instantiate `codeph  MediaPlayer`, passing an `codeph  android.content.Context` object to the constructor:
>   ```java
>   MediaPlayer mediaPlayer = new MediaPlayer(context);
>   ```
>   
>   
>1. Provide a frame layout ( `codeph  android.widget.FrameLayout`) to hold a `codeph  ViewGroup` of `codeph  mediaPlayer`:
>   
>   ```java
>   FrameLayout playerFrame = (FrameLayout) _viewGroup.findViewById(R.id.playerFrame);
>   ```
>   
>   Below is the code snippet to create `codeph  _viewGroup`.
>   
>   ```
>   @Override 
>    public ViewGroup onCreateView(LayoutInflater inflater, ViewGroup container, 
>    Bundle savedInstanceState) { 
>    _viewGroup = (ViewGroup) inflater.inflate( 
>    R.layout.fragment_player, container, false); 
>    return _viewGroup; 
>    }
>   ```
>   
>   
>1. Place a view of `codeph  mediaPlayer` inside the frame layout:
>   ```java
>   playerFrame.addView(mediaPlayer.getView());
>   ```
>   
>   
>   
