---
description: Instant-on preloads parts of the media on one or more channels. After a user selects or switches channels, the content starts sooner because some of the buffering has already completed.
seo-description: Instant-on preloads parts of the media on one or more channels. After a user selects or switches channels, the content starts sooner because some of the buffering has already completed.
seo-title: Instant-on
title: Instant-on
---

# Instant-on

When your player is in the `codeph PTMediaPlayerStatusReady` status, call `codeph prepareToPlay` to preload and process some of the content for later playback.


>[!TIP]
>
>If you do not call`codeph prepareToPlay`, calling `codeph play` automatically calls `codeph prepareToPlay` first. The preloading and processing is completed at this time.

completes some or all of the following tasks for `codeph prepareToPlay`:
* If the metadata key `codeph kSyncCookiesWithAVAsset` is set,  makes one request to the original M3U8 file to synchronize cookies.
* Loads DRM metadata keys.
* Creates and prepares some structures, elements, or assets that are needed for playing content.

>[!TIP]
>
>The`codeph PTMediaPlayer` and `codeph PTMediaPlayerItem` `codeph prepareToPlay` methods are equal. To avoid creating a separate `codeph PTMediaPlayer` instance for each asset, use the `codeph PTMediaPlayerItem` method.
Instant-on helps you launch multiple media player instances, or media-player item loader instances, simultaneously in the background and buffer video streams in all of these instances. When a user changes the channel, and the stream has buffered properly, calling `codeph play` on the new channel starts the playback sooner.

