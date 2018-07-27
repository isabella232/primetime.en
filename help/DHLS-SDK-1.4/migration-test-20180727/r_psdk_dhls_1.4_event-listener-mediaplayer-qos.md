---
description: dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering or seeking.
seo-description: dispatches quality of service (QoS) events to notify your application about events that could influence the computation of QoS statistics, such as buffering or seeking.
seo-title: QoS events
title: QoS events
uuid: e4c64537-0574-4c31-a796-6610592b5297
index: n
internal: n
snippet: y
translate: y
---

# QoS events


>`MediaPlayer`
>| Event |Meaning |
>|---|---|
>| `BufferEvent.[BUFFERING_END](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/BufferEvent.html#BUFFERING_END)` |Buffering is complete. |
>| `BufferEvent.[BUFFERING_BEGIN](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/BufferEvent.html#BUFFERING_BEGIN)` |Buffering has started. |
>| `SeekEvent.[SEEK_COMPLETED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/SeekEvent.html#SEEK_END)` |Seeking is complete. |
>| `SeekEvent.[SEEK_BEGIN](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/SeekEvent.html#SEEK_BEGIN)` |Seeking is starting. |
>| `SeekEvent.[SEEK_POSITION_ADJUSTED](http://help.adobe.com/en_US/primetime/api/psdk/asdoc-dhls_1.4/com/adobe/mediacore/events/SeekEvent.html#SEEK_POSITION_ADJUSTED)` | <!-- PH element: phrases/primetime-sdk-name --> changed the seek position as a result of current advertising policies. |

