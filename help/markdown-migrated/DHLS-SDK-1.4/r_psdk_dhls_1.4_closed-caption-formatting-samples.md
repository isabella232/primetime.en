---
---

## Example 1: Specify format values explicitly {#section_BD7B48F3B66D4E9290E1CB2F464E08E4}

```
private function onStatusChanged(event:MediaPlayerStatusChangeEvent):void { 
 var formatBuilder:TextFormatBuilder = new TextFormatBuilder(); 
 formatBuilder.font = Font.DEFAULT, 
 formatBuilder.fontSize = FontSize.DEFAULT, 
 formatBuilder.fontEdge = FontEdge.DEFAULT, 
 formatBuilder.fontColor = Color.DEFAULT, 
 formatBuilder.backgroundColor = Color.DEFAULT, 
 formatBuilder.fillColor = Color.DEFAULT, 
 formatBuilder.edgeColor = Color.DEFAULT, 
 formatBuilder.fontOpacity = .DEFAULT_OPACITY, 
 formatBuilder.backgroundOpacity = Font.DEFAULT_OPACITY, 
 formatBuilder.fillOpacity = TextFormat.DEFAULT_OPACITY 
 mediaPlayer.set CCStyle(formatBuilder.toTextFormat()); 
} 

```
## Example 2: Specify format values in parameters {#section_147036D7C31C4010A5A7DF49997014A9}

```
/** 
* Constructor using parameters to initialize a TextFormat. 
* 
* @param font 
* The desired font. 
* @param fontSize 
* The desired text size. 
* @param fontEdge 
* The desired font edge. 
* @param fontColor 
* The desired font color. 
* @param backgroundColor 
* The desired background color. 
* @param fillColor 
* The desired fill color. 
* @param edgeColor 
* The desired color to draw the text edges. 
* @param fontOpacity 
* The desired font opacity. 
* @param backgroundOpacity 
* The desired background opacity. 
* @param fillOpacity 
* The desired fill opacity. 
*/ 
public function TextFormatBuilder(font:Font, fontSize:FontSize, fontEdge:FontEdge, 
 fontColor:Color, backgroundColor:Color, 
 fillColor:Color, edgeColor:Color, fontOpacity:int, 
 backgroundOpacity:int, fillOpacity:int); 
/** 
* Creates a TextFormat with the parameters supplied to this builder. 
*/ 
public function toTextFormat():TextFormat; 
... 

```
