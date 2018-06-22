---
---

>```
>public function TextFormat( 
> font:String = default, 
> size:String = default, 
> fontEdge:String = default, 
> fontColor:String = default, 
> backgroundColor:String = default, 
> fillColor:String = default, 
> edgeColor:String = default, 
> fontOpacity:int, 
> backgroundOpacity:int, 
> fillOpacity:int)
>```
>
>>[!TIP]
>>
>>In options that define default values (for example,`codeph  DEFAULT`), that value refers to what the setting was when the caption was originally specified.
>
<table frame="all" colsep="1" rowsep="1" id="table_87205DEFEE384AF4AF83952B15E18A42"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="25*" /> 
  <colspec colnum="2" colname="2" colwidth="75*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry"> Format </th> 
    <th colname="2" class="entry"> Description </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"> Font </td> 
    <td colname="2"> <p>The font type. </p> <p>Can be set only to a value that is defined by the <span class="codeph"> ClosedCaptionStyles.FONT </span> array and represents, for example, monospaced with or without serifs. 
      <codeblock class="syntax actionscript">
        public static const FONT :Array = [ 
       <discoiqbr /> AVCaptionStyle.DEFAULT, 
       <discoiqbr /> AVCaptionStyle.MONOSPACE_WITH_SERIFS, 
       <discoiqbr /> AVCaptionStyle.MONOSPACED_WITHOUT_SERIFS, 
       <discoiqbr /> AVCaptionStyle.PROPORTIONAL_WITH_SERIFS, 
       <discoiqbr /> AVCaptionStyle.PROPORTIONAL_WITHOUT_SERIFS, 
       <discoiqbr /> AVCaptionStyle.CASUAL, 
       <discoiqbr /> AVCaptionStyle.CURSIVE, 
       <discoiqbr /> AVCaptionStyle.SMALL_CAPITALS 
       <discoiqbr /> ]; 
      </codeblock> </p> <p type="tip">Note:  The actual fonts that are available on a device might vary, and substitutions are used when necessary. Monospace with serifs is typically used as a substitute, although this substitution can be system specific. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Size </td> 
    <td colname="2"> <p>The caption's size. </p> <p> Can be set only to a value defined by the <span class="codeph"> ClosedCaptionStyles.FONT_SIZE </span> array: 
      <ul compact="yes" id="ul_544BFC7A46474A74839477108F1AB1E9"> 
       <li id="li_A592ED46B8DF4D8FAD7AF3BD931A712B"> <span class="codeph"> MEDIUM </span> - The standard size </li> 
       <li id="li_4F8CEDE54965430EB707DD3D5B2E3F87"> <span class="codeph"> LARGE </span> - Approximately 30% larger than medium </li> 
       <li id="li_D78D823883F54D869118BAB58257E377"> <span class="codeph"> SMALL </span> - Approximately 30% smaller than medium </li> 
       <li id="li_9299C13408584A38835F8D91BD048083"> <span class="codeph"> DEFAULT </span> - The default size for the caption; the same as medium </li> 
      </ul></p> <p type="tip">Note:  You can change the font size of WebVTT captions by changing the size parameter for the <span class="codeph"> DefaultMediaPlayer.ccStyles setter </span> function. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Font edge </td> 
    <td colname="2"> <p>The effect used for the font edge, such as raised or none. </p> <p>Can be set only to a value that is defined by the <span class="codeph"> ClosedCaptionStyles.FONT_EDGE </span> array. 
      <codeblock class="syntax actionscript">
        public static const FONT_EDGE :Array = [ 
       <discoiqbr /> AVCaptionStyle.DEFAULT, 
       <discoiqbr /> AVCaptionStyle.NONE, 
       <discoiqbr /> AVCaptionStyle.RAISED, 
       <discoiqbr /> AVCaptionStyle.DEPRESSED, 
       <discoiqbr /> AVCaptionStyle.UNIFORM, 
       <discoiqbr /> AVCaptionStyle.LEFT_DROP_SHADOW, 
       <discoiqbr /> AVCaptionStyle.RIGHT_DROP_SHADOW 
       <discoiqbr /> ]; 
      </codeblock> </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Font color </td> 
    <td colname="2"> <p>The font color. </p> <p>Can be set only to a value defined by the <span class="codeph"> ClosedCaptionStyles.COLOR </span> array. 
      <codeblock class="syntax actionscript">
        public static const COLOR :Array = [ 
       <discoiqbr /> AVCaptionStyle.DEFAULT, 
       <discoiqbr /> AVCaptionStyle.BLACK, 
       <discoiqbr /> AVCaptionStyle.GRAY, 
       <discoiqbr /> AVCaptionStyle.WHITE, 
       <discoiqbr /> AVCaptionStyle.BRIGHT_WHITE, 
       <discoiqbr /> AVCaptionStyle.RED, 
       <discoiqbr /> AVCaptionStyle.DARK_RED, 
       <discoiqbr /> AVCaptionStyle.BRIGHT_RED, 
       <discoiqbr /> AVCaptionStyle.GREEN, 
       <discoiqbr /> AVCaptionStyle.DARK_GREEN, 
       <discoiqbr /> AVCaptionStyle.BRIGHT_GREEN, 
       <discoiqbr /> AVCaptionStyle.BLUE, 
       <discoiqbr /> AVCaptionStyle.DARK_BLUE, 
       <discoiqbr /> AVCaptionStyle.BRIGHT_BLUE, 
       <discoiqbr /> AVCaptionStyle.YELLOW, 
       <discoiqbr /> AVCaptionStyle.DARK_YELLOW, 
       <discoiqbr /> AVCaptionStyle.BRIGHT_YELLOW, 
       <discoiqbr /> AVCaptionStyle.MAGENTA, 
       <discoiqbr /> AVCaptionStyle.DARK_MAGENTA, 
       <discoiqbr /> AVCaptionStyle.BRIGHT_MAGENTA, 
       <discoiqbr /> AVCaptionStyle.CYAN, 
       <discoiqbr /> AVCaptionStyle.DARK_CYAN, 
       <discoiqbr /> AVCaptionStyle.BRIGHT_CYAN ]; 
      </codeblock></p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Edge color </td> 
    <td colname="2"> <p>The color of the edge effect. </p> <p>Can be set to any of the values that are available for the font color. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Background color </td> 
    <td colname="2"> <p>The background character cell color. </p> <p>Can be set only to values that are available for the font color. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Fill color </td> 
    <td colname="2"> <p>The color of the background of the window in which the text is located. </p> <p>Can be set to any of the values that are available for the font color. </p> <p type="important">Note:  This does not apply to WebVTT captions, because WebVTT does not use this feature. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Font opacity </td> 
    <td colname="2"> <p>The opacity of the text. </p> <p>Expressed as a percentage from 0 (fully transparent) to 100 (fully opaque). <span class="codeph"> DEFAULT_OPACITY </span> for the font is 100. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Background opacity </td> 
    <td colname="2"> <p>The opacity of the background character cell. </p> <p>Expressed as a percentage from 0 (fully transparent) to 100 (fully opaque). <span class="codeph"> DEFAULT_OPACITY </span> for the background is 100. </p> </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"> Fill opacity </td> 
    <td colname="2"> <p>The opacity of the background of the caption window. </p> <p>Expressed as a percentage from 0 (fully transparent) to 100 (fully opaque). <span class="codeph"> DEFAULT_OPACITY </span> for fill is 0. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
