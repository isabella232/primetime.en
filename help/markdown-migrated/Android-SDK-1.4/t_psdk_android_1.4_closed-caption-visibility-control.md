---
description: You can control the visibility of closed captions. When visibility is on, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.
seo-description: You can control the visibility of closed captions. When visibility is on, the currently selected track is displayed. If you change which track is current, the visibility setting remains the same.
seo-title: Control closed-caption visibility
title: Control closed-caption visibility
---

# Control closed-caption visibility

>[!TIP]
>
>If closed caption text is displayed when the player enters the seek mode, the text no longer displays after the seek completes. Instead, after a few seconds, displays the next closed caption text in the video after the ending seek position.
>[!NOTE]
>
>The visibility values for closed captions are defined in`codeph  MediaPlayer.Visibility`.
>```java
>enum Visibility { 
> VISIBLE, 
> INVISIBLE 
>}
>```
>
>1. Wait for the MediaPlayer to have at least the PREPARED state (see []()).
>   
>1. To get the current visibility setting for closed captions, use the getter method in MediaPlayer, which returns a visibility value.
>       
>       ```java
>       Visibility getCCVisibility() throws IllegalStateException;
>       ```
>       
>   
>1. To change the visibility for closed captions, use the setter method, passing a visibility value from `codeph  MediaPlayer.Visibility`.
>       
>       ```java
>       mediaPlayer.setCCVisibility(Visibility.VISIBLE);
>       ```
>       
>   
>   
