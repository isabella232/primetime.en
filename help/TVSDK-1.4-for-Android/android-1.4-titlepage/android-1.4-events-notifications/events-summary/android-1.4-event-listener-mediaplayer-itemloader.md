---
description: TVSDK dispatches media player item events in response to loading a media item.
seo-description: TVSDK dispatches media player item events in response to loading a media item.
seo-title: Loader events
title: Loader events
uuid: b1eccc13-281a-40ef-94c9-53977cc85399
index: y
internal: n
snippet: y
---

# Loader events{#loader-events}

TVSDK dispatches media player item events in response to loading a media item.

These events provide an alternative workflow. You are not required to implement this interface when creating a MediaPlayer. Use this when you want to have a `MediaPlayerItemLoader`.

To be notified about events related to loading a media player resource, register an implementation of `MediaPlayerItemLoader.LoaderListener` including the following events.

|  Event  | Meaning  |
|---|---|
| ` [onLoadComplete](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItemLoader.LoaderListener.html#onLoadComplete(com.adobe.mediacore.MediaPlayerItem))( [mediaPlayerItem](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItem.html) playerItem)`  | Media resource loading completed successfully.  |
| ` [onError](http://help.adobe.com/en_US/primetime/api/psdk/javadoc_1.4/com/adobe/mediacore/MediaPlayerItemLoader.LoaderListener.html#onError(com.adobe.ave.MediaErrorCode,%20java.lang.String))` | A problem occurred with media resource loading.  |

>[!NOTE]
>
>Also see `onLoadInfo (loadInfo)` under QoS events.

