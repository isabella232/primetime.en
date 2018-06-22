---
description: Full-event replay (FER) is a VOD asset that acts as a live/DVR asset, so your application must take steps to ensure that ads are placed correctly.
seo-description: Full-event replay (FER) is a VOD asset that acts as a live/DVR asset, so your application must take steps to ensure that ads are placed correctly.
seo-title: Enable ads in full-event replay
title: Enable ads in full-event replay
---

# Enable ads in full-event replay

For live content,  uses the metadata/cues in the manifest to determine where to place ads. However, sometimes live/linear content might resemble VOD content. For example, when live content completes, an `codeph  EXT-X-ENDLIST` tag is appended to the live manifest. For HLS, the `codeph  EXT-X-ENDLIST` tag means that the stream is a VOD stream. To correctly insert ads,  cannot automatically differentiate this stream from a typical VOD stream.

Your application must tell  whether the content is live or VOD by specifying the `codeph  AdSignalingMode`.

For a FER stream, the  server should not provide the list of ad breaks that need to be inserted on the timeline before starting the playback. This is the typical process for VOD content. Instead, by specifying a different signaling mode,  reads all the cue points from the FER manifest and goes to the ad server for each cue point to request an ad break. This process is similar to live/DVR content.

>[!TIP]
>
>In addition to each request that is associated with a cue point, makes an additional ad request for pre-roll ads.
>1. From an external source, such as vCMS, obtain the signaling mode that should be used.
>   
>1. Create the advertising-related metadata.
>   
>1. If the default behavior must be overwritten, specify the `codeph  AdSignalingMode` by using `codeph  AdvertisingMetadata.setSignalingMode`.
>   The valid values are `codeph  DEFAULT`, `codeph  SERVER_MAP`, and `codeph  MANIFEST_CUES`.
>   
>   >[!IMPORTANT]
>   >
>   >You must set the ad signaling mode before calling`codeph  prepareToPlay`. After  starts to resolve and place ads on the timeline, changes to the ad signaling mode are ignored. Set the mode when you create the `codeph  AuditudeSettings` object.
>   
>   
>1. Continue to playback.
>   
>   
