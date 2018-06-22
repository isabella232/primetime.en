---
---

>These events provide an alternative workflow. You are not required to implement this interface when creating a MediaPlayer. Use this when you want to have a `codeph MediaPlayerItemLoader`.
>
>
>To be notified about events related to loading a media player resource, register an implementation of `codeph MediaPlayerItemLoader.LoaderListener` including the following events.
>
>
><table frame="all" colsep="1" rowsep="1"> 
 <tgroup cols="2" colsep="1" rowsep="1" class="FormatA"> 
  <colspec colnum="1" colname="1" colwidth="41*" /> 
  <colspec colnum="2" colname="2" colwidth="59*" /> 
  <thead> 
   <tr rowsep="1"> 
    <th colname="1" class="entry">Event</th> 
    <th colname="2" class="entry">Meaning</th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItemLoader.LoaderListener.html#onLoadComplete(com.adobe.mediacore.MediaPlayerItem)" format="html" scope="external">onLoadComplete</a>(<a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItem.html" format="html" scope="external">mediaPlayerItem</a> playerItem)</span> </td> 
    <td colname="2">Media resource loading completed successfully.</td> 
   </tr> 
   <tr rowsep="1"> 
    <td colname="1"><span class="codeph"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItemLoader.LoaderListener.html#onError(com.adobe.ave.MediaErrorCode,%20java.lang.String)" format="html" scope="external">onError</a> </span></td> 
    <td colname="2">A problem occurred with media resource loading.</td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>
>>[!NOTE]
>>
>>Also see`codeph onLoadInfo (loadInfo)` under QoS events.
>
