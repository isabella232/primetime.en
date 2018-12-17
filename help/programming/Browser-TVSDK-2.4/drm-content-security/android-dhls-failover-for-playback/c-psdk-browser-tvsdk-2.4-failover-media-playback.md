---
description: For live and VOD media, Browser TVSDK starts playback by downloading the playlist that is associated with the middle-resolution bit rate and then downloading segments of the middle-resolution bit rate media that is defined by the playlist.
seo-description: For live and VOD media, Browser TVSDK starts playback by downloading the playlist that is associated with the middle-resolution bit rate and then downloading segments of the middle-resolution bit rate media that is defined by the playlist.
seo-title: Media playback
title: Media playback
uuid: 9aa0be9c-2520-4b0f-b690-28de861a47a7
index: y
internal: n
snippet: y
---

# Media playback{#media-playback}

For live and VOD media, Browser TVSDK starts playback by downloading the playlist that is associated with the middle-resolution bit rate and then downloading segments of the middle-resolution bit rate media that is defined by the playlist.

Browser TVSDK quickly selects the high-resolution bit rate playlist and its associated media and continues the downloading process.

## Missing playlist failover {#section_81A5822C108449E1A0E94A6E25DE9E8E}

When an entire playlist is missing, for example, when the M3U8 file specified in a top-level manifest file does not download, Browser TVSDK attempts to recover. If it cannot be recovered, your application determines the next step.

If the playlist that is associated with the middle-resolution bit rate is missing, Browser TVSDK searches for a variant playlist at the same resolution. If it finds the same resolution, it starts downloading the variant playlist and the segments from the matching position. If Browser TVSDK does not find the same resolution playlist, it will try to cycle through other bitrate playlists and their variants. An immediately lower bitrate is the first choice, then its variant, and so on. If all of the lower bitrate playlists and their variants are exhausted in the attempt to find a valid playlist, Browser TVSDK will go to the top bitrate and count down from there. If a valid playlist cannot be found, the process fails, and the player moves to the ERROR state.

Your application can determine how to handle this situation. For example, you might want to close the player activity and direct the user to the catalog activity. The event of interest is the status or state changed event, and the corresponding callback is the on status changed method. Here is code that monitors whether the player changes its internal state to ERROR:

```js
case AdobePSDK.MediaPlayerStatus.ERROR:  
var errorDesc = event.metadata.getValue('DESCRIPTION'); 
console.log(errorDesc); 
break; 

```

## Missing segment failover {#section_23924F24E44B4A798BD16D594FAC134D}

When a segment is missing, for example when a particular segment fails to download, Browser TVSDK attempts to recover through a variety of failover attempts. If it cannot recover, it issues an error.

If a segment is missing on the server because, for example, the manifest file is not present, the segment cannot be downloaded, and so on, Browser TVSDK attempts to fail over by trying the following options:

1. Attempt a failover to the same segment, at the same bit rate, in a variant file. 
1. Switch to an alternate bit rate (ABR switch) in the same file. For finding the alternate bit rate, TVSDK uses ABR rules. 
1. Cycle through every available bit rate in every available variant.

When TVSDK cannot obtain an alternative segment, it moves the player to ERROR state. It sends inner error code as `AdobePSDK.PSDKErrorCode.NETWORK_ERROR`. The application can decide how to handle this situation by implementing the appropriate listeners. 
