---
description: You can specify closed-caption formatting.
seo-description: You can specify closed-caption formatting.
seo-title: Examples  Caption formatting
title: Examples  Caption formatting
uuid: 291be475-ab27-4ef9-a298-143b7555c723
index: y
internal: n
snippet: y
---

# Examples: Caption formatting{#examples-caption-formatting}

You can specify closed-caption formatting.

## Example 1: Specify format values explicitly {#section_BD7B48F3B66D4E9290E1CB2F464E08E4}

```js
// Set CC style. 
var tf = new AdobePSDK.TextFormat( 
      AdobePSDK.TextFormat.FONT_DEFAULT, 
      AdobePSDK.TextFormat.COLOR_DEFAULT, 
      AdobePSDK.TextFormat.COLOR_DEFAULT, 
      AdobePSDK.TextFormat.FONT_EDGE_DEFAULT, 
      AdobePSDK.TextFormat.COLOR_DEFAULT, 
      AdobePSDK.TextFormat.COLOR_DEFAULT, 
      AdobePSDK.TextFormat.SIZE_DEFAULT, 
      AdobePSDK.TextFormat.DEFAULT_OPACITY, 
      AdobePSDK.TextFormat.DEFAULT_OPACITY, 
      AdobePSDK.TextFormat.DEFAULT_OPACITY; 
 mediaPlayer.CCStyle(tf);
```

>[!IMPORTANT]
>
>Browser TVSDK does not support font edge, fill color, or fill opacity.

