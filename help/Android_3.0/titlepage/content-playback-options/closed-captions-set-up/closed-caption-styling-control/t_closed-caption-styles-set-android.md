---
description: You can style the closed-caption text with TVSDK methods.
seo-description: You can style the closed-caption text with TVSDK methods.
seo-title: Set closed-caption styles
title: Set closed-caption styles
uuid: 44db36ab-ebb6-449b-8320-50adccab455f
index: y
internal: n
snippet: y
translate: y
---

# Set closed-caption styles

You can style the closed-caption text with TVSDK methods.


1. Wait for the media player to be in at least the `PREPARED` status.
1. Create a `TextFormatBuilder` instance.

   You can provide all the closed-caption styling parameters now or set them later. 


   TVSDK encapsulates closed-caption styling information in the `TextFormat` interface. The `TextFormatBuilder` class creates objects that implement this interface. 

   ```
   java   public TextFormatBuilder( 
      TextFormat.Font font, 
      TextFormat.Size size, 
      TextFormat.FontEdge fontEdge, 
      java.lang.String fontColor, 
      java.lang.String backgroundColor, 
      java.lang.String fillColor, 
      java.lang.String edgeColor, 
      int fontOpacity, 
      int backgroundOpacity, 
      int fillOpacity 
      java.lang.String bottomInset, 
      java.lang.String safeArea)
   ```

1. To obtain a reference to an object that implements the `TextFormat` interface, call the `TextFormatBuilder.toTextFormat` public method.

   This returns a `TextFormat` object that can be applied to the media player. 
   ```
   java   public TextFormat toTextFormat()
   ```

1. Optionally get the current closed-caption style settings by doing one of the following:

    * Get all the style settings with `MediaPlayer.getCCStyle`. The return value is an instance of the `TextFormat` interface.     
      ```
      java      /** 
      * @return the current closed captioning style.  
      * If no style was previously set, it returns a TextFormat object 
      * with default values for each attribute. 
      * @throws MediaPlayerException if media player was already released. 
      */ 
      public TextFormat getCCStyle() throws MediaPlayerException;
      ```

    
    * Get the settings one at a time through the `TextFormat` interface getter methods.     
      ```
      java      public java.lang.String getFontColor(); 
      public java.lang.String getBackgroundColor(); 
      public java.lang.String getFillColor(); // retrieve the font fill color 
      public java.lang.String getEdgeColor(); // retrieve the font edge color 
      public TextFormat.Size getSize(); // retrieve the font size 
      public TextFormat.FontEdge getFontEdge(); // retrieve the font edge type 
      public TextFormat.Font getFont(); // retrieve the font type 
      public int getFontOpacity(); 
      public int getBackgroundOpacity(); 
      public java.lang.String getBottomInset(java.lang.String bi); 
      public java.lang.String getSafeArea(java.lang.String sa);
      ```
    
    
    
1. To change the style settings, do one of the following:

    * Use the setter method `MediaPlayer.setCCStyle`, passing an instance of the `TextFormat` interface:     
      ```
      java      /** 
      * Sets the closed captioning style. Used to control the closed captioning font, 
      * size, color, edge and opacity.  
      * 
      * This method is safe to use even if the current media stream doesn't have closed 
      * captions. 
      * 
      * @param textFormat 
      * @throws MediaPlayerException 
      */ 
      public void setCCStyle(TextFormat textFormat) throws MediaPlayerException;
      ```
    
    * Use the `TextFormatBuilder` class, which defines individual setter methods. The `TextFormat` interface defines an immutable object so there are only getter methods and no setters. You can set the closed-caption styling parameters only with the `TextFormatBuilder` class: 
    
      ```
      java      // set font type 
      public void setFont(Font font)  
      public void setBackgroundColor(String backgroundColor) 
      public void setFillColor(String fillColor) 
      // set the font-edge color 
      public void setEdgeColor(String edgeColor)  
      // set the font size 
      public void setSize(Size size)  
      // set the font edge type 
      public void setFontEdge(FontEdge fontEdge)  
      public void setFontOpacity(int fontOpacity) 
      public void setBackgroundOpacity(int backgroundOpacity) 
      // set the font-fill opacity level 
      public void setFillOpacity(int fillOpacity)  
      public void setFontColor(String fontColor) 
      public void setBottomInset(String bi) 
      public void setSafeArea(String sa) 
      public void setTreatSpaceAsAlphaNum(bool)
      ```

      >[!IMPORTANT]
      >
      >**Color Settings:** In Android TVSDK 2.X, an enhancement was made to color styling of closed captions. The enhancement allows for setting closed caption colors using a hex string representing RGB color values. The RGB hex color representation is the familiar 6 byte string you use in applications such as Photoshop:       >
      >* FFFFFF = Black* 000000 = White* FF0000 = Red* 00FF00 = Green* 0000FF = Blue      >
      >
      >and so on.
      >
      >In your application, whenever you pass color styling information to `TextFormatBuilder`, you still use the `Color` enumeration as before, but now you must add `getValue()` to the color to get the value as a string. For example:       >
      >```
      >tfb = tfb.setBackgroundColor(TextFormat.Color.RED 
<b>.getValue()</b>);
      >```


    
    
    

   Setting the closed-caption style is an asynchronous operation, so it might take up to a few seconds for the changes to appear on the screen.
