---
description: When a segment is missing, for example when a particular segment fails to download, attempts to recover through a variety of failover attempts. If it cannot recover, it issues an error.
seo-description: When a segment is missing, for example when a particular segment fails to download, attempts to recover through a variety of failover attempts. If it cannot recover, it issues an error.
seo-title: Missing segment failover
title: Missing segment failover
---

# Missing segment failover

If a segment is missing on the server because, for example, the manifest file is not present, the segment cannot be downloaded, and so on,  attempts to fail over by attempting the following options:

1. Attempt a failover to the same segment, at the same bit rate, in a variant file.
1. Switch to an alternate bit rate (ABR switch) in the same file.
1. Cycle through every available bit rate in every available variant.
1. Skip the segment and issue a warning.
When  cannot obtain an alternative segment, it triggers a `codeph CONTENT_ERROR` error notification. This notification contains an inner notification with the `codeph DOWNLOAD_ERROR` code. If the stream with the problem is an alternate audio track,  generates the `codeph AUDIO_TRACK_ERROR` error notification.

If the video engine is continuously unable to obtain segments, it limits continuous segment skips to 5, after which playback is stopped and  issues a `codeph NATIVE_ERROR` with the code 5.

>[!NOTE] {type="restriction"}
>
>Here are some restrictions you should be aware of:
>* The adaptive bit rate (ABR) control parameters are not taken into consideration when a failover occurs.
>  This is because the failover mechanism is designed to use any of the currently available playlists, regardless of their bit rate profile, as backup streams.
>  
>  
>* During a failover operation, there can be a profile switch.
>  If an error occurs during the download of one of the playlist segments, ABR control parameters such as min/max allowed bit rate are ignored.
>  
>  
>
>
