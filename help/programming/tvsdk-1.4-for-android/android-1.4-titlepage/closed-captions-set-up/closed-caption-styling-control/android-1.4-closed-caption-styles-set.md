---
description: You can style the closed-caption text with TVSDK methods.
seo-description: You can style the closed-caption text with TVSDK methods.
seo-title: Set closed-caption styles
title: Set closed-caption styles
uuid: ab99428b-0c23-48a1-a099-78213b180339
---

# Set closed-caption styles{#set-closed-caption-styles}

You can style the closed-caption text with TVSDK methods.

1. Wait for the media player to be in at least the PREPARED state.
1. Create a `TextFormatBuilder` instance.

   You can provide all the closed-caption styling parameters now or set them later.

   TVSDK encapsulates closed-caption styling information in the `TextFormat` interface. The `TextFormatBuilder` class creates objects that implement this interface.

   ```java
   public TextFormatBuilder( 
      Font font, 
      Size size, 
      FontEdge fontEdge, 
      Color fontColor, 
      Color backgroundColor, 
      Color fillColor, 
      Color edgeColor, 
      int fontOpacity, 
      int backgroundOpacity, 
      int fillOpacity)
   ```

1. To obtain a reference to an object that implements the `TextFormat` interface, call the `TextFormatBuilder.toTextFormat` public method.

   This returns a `TextFormat` object that can be applied to the media player. 

   ```java
   public TextFormat toTextFormat()
   ```

1. Optionally get the current closed-caption style settings by doing one of the following:

    * Get all the style settings with `MediaPlayer.getCCStyle`.

      The return value is an instance of the `TextFormat` interface.     
    
      ```js    
      /** 
      * @return the current closed captioning style.  
      * If no style was previously set, it returns a TextFormat object 
      * with default values for each attribute. 
      * @throws IllegalStateException if media player was already released. 
      */ 
      public TextFormat getCCStyle() throws IllegalStateException;
      ```

    * Get the settings one at a time through the `TextFormat` interface getter methods.     
    
      ```js    
      public Color getFontColor(); 
      public Color getBackgroundColor(); 
      public Color getFillColor(); // retrieve the font fill color 
      public Color getEdgeColor(); // retrieve the font edge color 
      public Size getSize(); // retrieve the font size 
      public FontEdge getFontEdge(); // retrieve the font edge type 
      public Font getFont(); // retrieve the font type 
      public int getFontOpacity(); 
      public int getBackgroundOpacity();
      ```

1. To change the style settings, do one of the following:

   >[!NOTE]
   >
   >You cannot change the size for WebVTT captions.

    * Use the setter method `MediaPlayer.setCCStyle`, passing an instance of the `TextFormat` interface:     
    
      ```js    
      /** 
      * Sets the closed captioning style. Used to control the closed captioning font, 
      * size, color, edge and opacity.  
      * 
      * This method is safe to use even if the current media stream doesn't have closed 
      * captions. 
      * 
      * @param textFormat 
      * @throws IllegalStateException 
      */ 
      public void setCCStyle(TextFormat textFormat) throws IllegalStateException;
      ```

    * Use the `TextFormatBuilder` class, which defines individual setter methods.

      The `TextFormat` interface defines an immutable object so there are only getter methods and no setters. You can set the closed-caption styling parameters only with the `TextFormatBuilder` class:

      ```js    
      // set font type 
      public void setFont(Font font)  
      public void setBackgroundColor(Color backgroundColor) 
      public void setFillColor(Color fillColor) 
      // set the font-edge color 
      public void setEdgeColor(Color edgeColor)  
      // set the font size 
      public void setSize(Size size)  
      // set the font edge type 
      public void setFontEdge(FontEdge fontEdge)  
      public void setFontOpacity(int fontOpacity) 
      public void setBackgroundOpacity(int backgroundOpacity) 
      // set the font-fill opacity level 
      public void setFillOpacity(int fillOpacity)  
      public void setFontColor(Color fontColor)
      ```

   Setting the closed-caption style is an asynchronous operation, so it might take up to a few seconds for the changes to appear on the screen.
