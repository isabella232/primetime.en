---
title: PSDK Error Codes
description: Information about various error codes, warnings, and native error codes.
---

# PSDK Error Codes {#psdk-error-codes}

Read on to know about PSDK error codes, warnings, and native error codes.

## Errors

The following table provides detailed information about ERROR type notifications. Most errors contain relevant metadata; for example, URL of the resource that failed to download. Some notifications contain metadata to specify whether the problem occurred in the main video content, in the alternate audio content, or in an ad.

|| PSDK Error Name | PSDK Error Code | Description |
|----|---|---|---|
| 1 | SUCCESS | 0 | Operation performed by underlying API is successful. |
| 2 | INVALID_ARGUMENT | 1 | Data or format of argument provided to underlying API is invalid. |
| 3 | NULL_POINTER | 2 | One of the argument passed in is NULL Or one of the internal members was not initialized. |
| 4 | ILLEGAL_STATE | 3 | The operation is not supported in current player state. |
| 5 | INTERFACE_NOT_FOUND | 4 | The interfaceCast method throws this error when the requested interface is not implemented/inherited by this. |
| 6 | CREATION_FAILED | 5 | Creation of one of the internal resources failed. |
| 7 | UNSUPPORTED_OPERATION | 6 | The requested operation is currently not supported. |
| 8 | DATA_NOT_AVAILABLE | 7 | The requested data is currently not available. |
| 9 | SEEK_ERROR | 8 | An error has occurred while performing a seek operation. |
| 10 | UNSUPPORTED_FEATURE | 9 | This feature/function is not supported. |
| 11 | RANGE_ERROR | 10 | Specified value is out of range. |
| 12 | CODEC_NOT_SUPPORTED | 11 | Given stream's Audio/Video Codec is not supported by TVSDK or by underlying device. |
| 13 | MEDIA_ERROR | 12 | The specified media is not found. |
| 14 | NETWORK_ERROR | 13 | An Error has occurred while downloading a fragment or segment(both video and audio). |
| 15 | GENERIC_ERROR | 14 | Generic error event. Not actually issued by TVSDK. This is only a marker for the end of the range of numerical codes corresponding to TVSDK error events. |
| 16 | INVALID_SEEK_TIME | 15 | The seek time provided is invalid. |
| 17 | AUDIO_TRACK_ERROR | 16 | An error related to an audio track occurred (Alternate Audio) |
| 18 | ACCESS_FROM_DIFFERENT_THREAD | 17 | PSDK API is called from different thread than the thread in which PSDK was initialized. |
| 19 | ELEMENT_NOT_FOUND | 18 | The element is not found. |
| 20 | NOT_IMPLEMENTED | 19 | Feature not implemented. |
| 21 | PRE_ROLL_DISABLED | 20 | The preroll has been disabled via AdvertisingMetadata. |
| 22 | PLAYBACK_NOT_AUTHORIZED | 57 | HLS playback has not been enabled in the Flash Player. See AuthorizedFeatures.enableMediaPlayerHLSPlayback(). |
| 23 | NETWORK_TIMEOUT | 58 | Network Timed out while fetching a resource/connecting server. |

## Warnings

The following table provides detailed information about WARN type notifications.
Most warnings contain relevant metadata; for example, the URL of the resource that failed to download. Some notifications contain metadata to specify whether the problem occurred in the main video content, in the alternate audio content, or in an ad.

| | Error Name | Code | Description |
| --- | --- | --- | --- |
| 1 | PLAYBACK_OPERATION_FAILED | 200 | There was an error during playback operation. A playback-related operation has failed | but playback may continue." |
| 2 | NATIVE_WARNING | 201 | The low-level AVE library issued an error. | |
| 3 | AD_RESOLVER_FAILED | 202 | Ad plugin failed to resolve ads. | |
| 4 | AD_MANIFEST_LOAD_FAILED | 203 | Failed to load the Ad manifest. | |
| 5 | AD_RESOLUTION_IN_PROGRESS | 204 | Operation for Resolving Ads is in progress. | |

## Info

| | Error Name | Code | Description |
| --- | --- | --- | --- |
| 1 | REVENUE_OPTIMIZATION_REPORTING | 300 | TVSDK detailed Notifications for further reporting and analysis. |

## Native Error Codes

The Video Encoder interface of the AVE returns these video playback notifications in the NATIVE_ERROR metadata object.

| | Native Error Name | Native Error Code | Description |
|---|---|---|---|
| 1 | END_OF_PERIOD | -1 | End of period. |
| 2 | SUCCESS | 0 | Operation successful. |
| 3 | ASYNC_OPERATION_IN_PROGRESS | 1 | Asynchronous operation. The operation request has been made. Success/ failure information will be available later. |
| 4 | EOF | 2 | Operation not possible due to end of file (EOF) condition. |
| 5 | DECODER_FAILED | 3 | The decoder failed at runtime. |
| 6 | DEVICE_OPEN_ERROR | 4 | Failed to open hardware decoder. |
| 7 | FILE_NOT_FOUND | 5 | Resource cannot be located. |
| 8 | GENERIC_ERROR | 6 | Generic error. |
| 9 | IRRECOVERABLE_ERROR | 7 | An error condition that the Video Engine cannot recover from. |
| 10 | LOST_CONNECTION_RECOVERABLE | 8 | Network error, trying to recover. |
| 11 | NO_FIXED_SIZE | 9 | The size of the resource cannot be determined. |
| 12 | NOT_IMPLEMENTED | 10 | Feature not implemented. |
| 13 | OUT_OF_MEMORY | 11 | Out of memory. |
| 14 | PARSE_ERROR | 12 | Error while parsing the media file. |
| 15 | SIZE_UNKNOWN | 13 | The resource has a size, but it is unknown. |
| 16 | UNDER_FLOW | 14 | Underflow condition. |
| 17 | UNSUPPORTED_CONFIG | 15 | Configuration is not supported. |
| 18 | UNSUPPORTED_OPERATION | 16 | Operation is not supported. |
| 19 | WAITING_FOR_INIT | 17 | Not yet initialized. |
| 20 | INVALID_PARAMETER | 18 | Invalid parameter. |
| 21 | INVALID_OPERATION | 19 | Operation not permitted. |
| 22 | OP_ONLY_ALLOWED_IN_PAUSED_STATE | 20 | The operation is allowed only while paused. |
| 23 | OP_INVALID_WITH_AUDIO_ONLY_FILE | 21 | Operation cannot be used on audio only files. |
| 24 | PREVIOUS_STEP_SEEK_IN_PROGRESS | 22 | Previous seek operation is still in progress. |
| 25 | SOURCE_NOT_SPECIFIED | 23 | Resource not specified. |
| 26 | RANGE_ERROR | 24 | Specified value is out of range. |
| 27 | INVALID_SEEK_TIME | 25 | Invalid seek time. |
| 28 | FILE_STRUCTURE_INVALID | 26 | The file specified does not conform to the expected syntax. |
| 29 | COMPONENT_CREATION_FAILURE | 27 | An essential component could not be created. |
| 30 | DRM_INIT_ERROR | 28 | Failed to create DRM context. |
| 31 | CONTAINER_NOT_SUPPORTED | 29 | Container type is not supported. |
| 32 | SEEK_FAILED | 30 | Seek failed. |
| 33 | CODEC_NOT_SUPPORTED | 31 | Unsupported codec. |
| 34 | NETWORK_UNAVAILABLE | 32 | Network is not available. |
| 35 | NETWORK_ERROR | 33 | Error getting data from the Network. |
| 36 | OVERFLOW | 34 | Overflow. |
| 37 | VIDEO_PROFILE_NOT_SUPPORTED | 35 | Unsupported video profile. |
| 38 | PERIOD_NOT_LOADED | 36 | An operation was attempted on a HOLD period or a period that has not yet been loaded. |
| 39 | INVALID_REPLACE_DURATION | 37 | The replace duration specified is invalid or extends past the end of the stream. |
| 40 | CALLED_FROM_WRONG_THREAD | 38 | API can't be called from the wrong thread. Mostly, for API elements that should be called from Main thread only. |
| 41 | FRAGMENT_READ_ERROR | 39 | Fragment read error. No failover present. Engine will try to read the next fragment. |
| 42 | ABORTED | 40 | The operation was aborted by an explicit Abort or Destroy call. |
| 43 | UNSUPPORTED_HLS_VERSION | 41 | Cannot play this version of HLS media. |
| 44 | CANNOT_FAIL_OVER | 42 | Cannot fail over. |
| 45 | HTTP_TIME_OUT | 43 | HTTP download has timed out. |
| 46 | NETWORK_DOWN | 44 | The user's network connection is down. Playback could stop any moment and will resume when the connection is available. |
| 47 | NO_USABLE_BITRATE_PROFILE | 45 | No usable bit rate profile found in the stream. |
| 48 | BAD_MANIFEST_SIGNATURE | 46 | The manifest has a bad signature. It failed the manifest signing test. |
| 49 | CANNOT_LOAD_PLAYLIST | 47 | Cannot load a playlist. |
| 50 | REPLACEMENT_FAILED | 48 | Replacement specified in an Insert API could not succeed. This means that the insertion succeeded but replacement did not. Replacement could fail if the manifest to be replaced has been removed from the timeline. |
| 51 | SWITCH_TO_ASYMMETRIC_PROFILE | 49 | DRM is switching to an asymmetric profile. All the profiles are expected to be aligned in duration. If not, this warning will be thrown, and there may be jumps in the playback. |
| 52 | LIVE_WINDOW_MOVED_BACKWARD | 50 | Live window is expected to move forward only. If not, this warning will be thrown, and the window will not be read. Because of that, there may be jumps (or stop / long pause) in the playback. |
| 53 | CURRENT_PERIOD_EXPIRED | 51 | Live window moved beyond the current period. |
| 54 | CONTENT_LENGTH_MISMATCH | 52 | The content-length reported by the HTTP server did not match the actual media size. |
| 55 | PERIOD_HOLD | 53 | The media reader is unable to read further because it has reached the time set by setHoldAt API. |
| 56 | LIVE_HOLD | 54 | The media reader is unable to load segments because it has reached the end of the live window. Segment loading will resume when the server ads new media to the live window. This state is usually reached if:<ul><li>The bufferTime is too high (equal to or higher than the live window duration). </li><li>A combination of one or more of insert/ erase API replaced more media than it added.</li><li>The next period is a live period with a pending media replacement (due to InsertBy API call)</li></ul> |
| 57 | BAD_MEDIA_INTERLEAVING | 55 | The audio and video interleaving in the media is not done properly. This is a packaging error. The warning is dispatched when the difference exceeds two seconds. |
| 58 | DRM_NOT_AVAILABLE | 56 | |
| 59 | PLAYBACK_NOT_AUTHORIZED | 57 | HLS playback has not been enabled in the Flash Player. See AuthorizedFeatures.enableHLSPlayback. |
| 60 | BAD_MEDIA_SAMPLE_FOUND | 58 | The decoder received a bad sample that cannot be decoded. This is usually not a fatal error but indicates that there may be glitches in the audio/video. Too many instances of this error indicate a bad encoding or bad file. |
| 61 | RANGE_SPANS_READ_HEAD | 59 | After playback has started, the Insert/Replace range should not contain the read head. |
| 62 | POSTROLL_WITH_LIVE_NOT_ALLOWED | 60 | Post-roll insertions are not allowed on a live media. They are, however, allowed after the server marks the media as complete. |
| 63 | INTERNAL_ERROR | 61 | A very rare issue that should never happen. |
| 64 | SPS_PPS_FOUND_OUTSIDE_AVCC | 62 | The stream does not follow the packaging recommendation of always putting H264 SPS/PPS in an AVCC. Seek / playback issues might be seen. |
| 65 | PARTIAL_REPLACEMENT | 63 | Replacement specified in an Insert API was only partially done. This happens when replaceDuration spans over the timeline duration. |
| 66 | RENDITION_M3U8_ERROR | 64 | Rendition playlist had an error loading. This is only for AVE, not for FlashPlayer. |
| 67 | NULL_OPERATION | 65 | Operation does not do anything. |
| 68 | SEGMENT_SKIPPED_ON_FAILURE | 66 | Segment cannot be played and is skipped on failure. |
| 69 | INCOMPATIBLE_RENDER_MODE | 67 | Incompatible render mode. |
| 70 | PROTOCOL_NOT_SUPPORTED | 68 | The Web protocol used in the URL is not supported. |
| 71 | PARSE_ERROR_INCOMPATIBLE_VERSION | 69 | Error while parsing media file. |
| 72 | MANIFEST_FILE_UNEXPECTEDLY_CHANGED | 70 | Manifest file was changed in an unexpected manner. |
| 73 | CANNOT_SPLIT_TIMELINE | 71 | Cannot perform a split operation on a timeline. |
| 74 | CANNOT_ERASE_TIMELINE | 72 | Cannot perform an erase operation on a timeline. |
| 75 | DID_NOT_GET_NEXT_FRAGMENT | 73 | Did not get the next fragment. |
| 76 | NO_TIMELINE | 74 | No timeline present in an internal data structure. |
| 77 | LISTENER_NOT_FOUND | 75 | No listener found in an internal data structure. |
| 78 | AUDIO_START_ERROR | 76 | Unable to start audio. |
| 79 | NO_AUDIO_SINK | 77 | No audio sink present in an internal data structure. |
| 80 | FILE_OPEN_ERROR | 78 | Unable to open file. |
| 81 | FILE_WRITE_ERROR | 79 | Unable to write to a file. |
| 82 | FILE_READ_ERROR | 80 | Unable to read from a file. |
| 83 | ID3PARSE_ERROR | 81 | There was an error parsing ID3 data. |
| 84 | SECURITY_ERROR | 82 | Loading the content failed because of security restrictions. |
| 85 | TIMELINE_TOO_SHORT | 83 | The timeline duration is too short. If this is a live stream, frequent buffering may happen. |
| 86 | AUDIO_ONLY_STREAM_START | 84 | The stream has been switched to an audio-only stream. |
| 87 | AUDIO_ONLY_STREAM_END | 85 | The stream has been switched from audio-only to a stream with video. |
| 88 | KEY_NOT_FOUND | 87 | Key cannot be found. |
| 89 | INVALID_KEY | 88 | The key is invalid. |
| 90 | KEY_SERVER_NOT_FOUND | 89 | Key server does not return a key. |
| 91 | MAIN_MANIFEST_UPDATE_TO_BE_HANDLED | 90 | Cannot handle main manifest update. |
| 92 | UNREPORTED_TIME_DISCONTINUITY_FOUND | 91 | Unreported time (PTS) discontinuity found. |
| 93 | UNMATCHED_AV_DISCONTINUITY_FOUND | 92 | Unmatched Audio and Video discontinuity found. |
| 94 | TRICKPLAY_ENDED_DUE_TO_ERROR | 93 | There was an error while playing media in trick play mode. Trick play mode is ended and the stream is paused. Call Play() to play the media in normal mode. |
| 95 | LIVE_WINDOW_MOVED_AHEAD | 95 | The player is out of the live window and must seek forward to catch up. |
