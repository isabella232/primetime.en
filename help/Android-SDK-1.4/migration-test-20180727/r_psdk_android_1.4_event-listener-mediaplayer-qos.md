---
description: dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering or seeking.
seo-description: dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering or seeking.
seo-title: QoS events
title: QoS events
uuid: 42b47a64-4db8-4dd2-b1a0-00e1048145f0
index: n
internal: n
snippet: y
translate: y
---

# QoS events


>`MediaPlayer.QOSEventListener`
>| Event |Meaning |
>|---|---|
>| [onBufferComplete](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onBufferComplete())  |Buffering is complete. |
>| [onBufferStart](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onBufferStart())  |Buffering has started. |
>| [onLoadInfo](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onLoadInfo(com.adobe.mediacore.qos.LoadInfo))(loadInfo)  |A fragment has successfully downloaded. |
>|  [onOperationFailed](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html)(MediaPlayerNotification.[Warning](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerNotification.Warning.html) warning)  |A recoverable error has occurred. |
>| [onSeekComplete](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onSeekComplete(long))(long adjustedTime)  |Seeking is complete. |
>| [onSeekStart](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayer.QOSEventListener.html#onSeekStart())  |Seeking is starting. |

