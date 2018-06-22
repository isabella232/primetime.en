---
description: You can control the visibility of closed captions. When visibility has been enabled, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.
seo-description: You can control the visibility of closed captions. When visibility has been enabled, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.
seo-title: Control closed-caption visibility
title: Control closed-caption visibility
---

# Control closed-caption visibility

>[!TIP]
>
>If closed caption text is displayed when the player enters seek mode, the text no longer displays after the seek completes. Instead, after a few seconds, displays the next closed caption text in the video after the ending seek position.
>The visibility values for closed captions are defined in `codeph  MediaPlayer.Visibility`.
>```java
>enum Visibility { 
> VISIBLE, 
> INVISIBLE 
>}
>```
>
>
>1. Wait for the `codeph  MediaPlayer` to be in at least the PREPARED status.
>   For more information, see[]().
>   
>1. To get the current visibility setting for closed captions, use the getter method in `codeph  MediaPlayer`, which returns a visibility value.
>   ```java
>   MediaPlayer.Visibility getCCVisibility() throws MediaPlayerException;
>   ```
>   
>   
>1. To change the visibility for closed captions, use the setter method, passing a visibility value from `codeph  MediaPlayer.Visibility`.
>   For example:
>   ```java
>   mediaPlayer.setCCVisibility(MediaPlayer.Visibility visibility);
>   ```
>   
>   
>   
