---
description: Full-event replay (FER) is a VOD asset that acts as a live/DVR asset, so your application must take steps to ensure that ads are placed correctly.
seo-description: Full-event replay (FER) is a VOD asset that acts as a live/DVR asset, so your application must take steps to ensure that ads are placed correctly.
seo-title: Enable ads in full-event replay
title: Enable ads in full-event replay
uuid: d6ce85e3-5a36-4cb4-84bd-ce94bb5ff455
index: n
internal: n
snippet: y
translate: y
---

# Enable ads in full-event replay

For live content,  <!-- PH element: phrases/primetime-sdk-name --> uses the metadata/cues in the manifest to determine where to place ads. However, sometimes live/linear content might resemble VOD content. For example, when live content completes, an `EXT-X-ENDLIST` tag is appended to the live manifest. For HLS, the `EXT-X-ENDLIST` tag means that the stream is a VOD stream.  <!-- PH element: phrases/primetime-sdk-name --> cannot automatically differentiate this stream from a normal VOD stream to correctly insert ads.
Your application must tell  <!-- PH element: phrases/primetime-sdk-name --> whether the content is live or VOD by specifying the `AdSignalingMode`. 
For a FER stream, the  <!-- PH element: phrases/auditude-name-long --> server should not provide the list of ad breaks that need to be inserted on the timeline before starting the playback. This is the typical process for VOD content. Instead, by specifying a different signaling mode, <!-- PH element: phrases/primetime-sdk-name --> reads all the cue points from the FER manifest and goes to the ad server for each cue point to request an ad break. This process is similar to live/DVR content.
In addition to each request that is associated with a cue point,  <!-- PH element: phrases/primetime-sdk-name --> makes an additional ad request for pre-roll ads.

>1. From an external source, such as vCMS, obtain the signaling mode that should be used.
>1. Create the advertising-related metadata.
>1. If the default behavior must be overwritten, specify the `AdSignalingMode` by using `AdvertisingMetadata.setSignalingMode`.
>   The valid values are `DEFAULT, SERVER_MAP`, and `MANIFEST_CUES`. 
>   You must set the ad signaling mode before calling `prepareToPlay`. After  <!-- PH element: phrases/primetime-sdk-name --> starts to resolve and place ads on the timeline, changes to the ad signaling mode are ignored. Set the mode when you create the `AuditudeSettings` object. 
>
>1. Continue to playback.
