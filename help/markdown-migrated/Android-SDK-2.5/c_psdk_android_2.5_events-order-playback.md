---
description: dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-description: dispatches events/notifications in generally expected sequences. Your player can implement actions based on events in the expected sequence.
seo-title: Order of playback events
title: Order of playback events
---

# Order of playback events

<a id="section_09D3ED5F4886460A8669EC362E57F5F8"></a>

The following examples show the order of some events that occur during playback.

When successfully loading a media resource through `codeph MediaPlayer.replaceCurrentResource`, the order of events is:
1. `codeph MediaPlayerEvent.STATUS_CHANGED` with status `codeph MediaPlayerStatus.INITIALIZING`
1. `codeph MediaPlayerEvent.STATUS_CHANGED` with status `codeph MediaPlayerStatus.INITIALIZED`
>[!TIP]
>
>Load your media resource on the main thread. If you load a media resource on a background thread, this operation or subsequent operations might throw an error, such as`codeph MediaPlayerException`, and exit.
When preparing for playback through`codeph MediaPlayer.prepareToPlay`, the order of events is:
1. `codeph MediaPlayerEvent.STATUS_CHANGED` with status `codeph MediaPlayerStatus.PREPARING`
1. `codeph MediaPlayerEvent.TIMELINE_UPDATED` if ads were inserted.
1. `codeph MediaPlayerEvent.STATUS_CHANGED` with status `codeph MediaPlayerStatus.PREPARED`
For live/linear streams, during playback as the playback window advances and additional opportunities are resolved, the order of events is:
1. `codeph MediaPlayerEvent.ITEM_UPDATED`
1. `codeph MediaPlayerEvent.TIMELINE_UPDATED` if ads were inserted

