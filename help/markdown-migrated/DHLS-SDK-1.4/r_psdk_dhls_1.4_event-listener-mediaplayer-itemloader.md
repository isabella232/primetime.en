---
---

>These events provide an alternative workflow. You are not required to implement this interface when creating a `codeph MediaPlayer`. Use this when you want to have a `codeph MediaPlayerItemLoader`.
>
>
>To be notified about events related to loading a media player resource, register listeners for the following events with the `codeph MediaPlayerItemLoader` object.
>
>
<table frame="all" colsep="1" rowsep="1"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="41*" /> 
  <colspec colnum="2" colname="2" colwidth="59*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Event </th> 
    <th colname="2" class="entry">Meaning </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">MediaPlayerItemLoader.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/MediaPlayerItemLoader.html#event:completed" format="html" scope="external">completed</a></span></td> 
    <td colname="2">Media resource loading completed successfully. </td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph">MediaPlayerItemLoader.<a href="http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/MediaPlayerItemLoader.html#event:failed" format="html" scope="external">failed</a></span></td> 
    <td colname="2">A problem occurred with media resource loading. </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
