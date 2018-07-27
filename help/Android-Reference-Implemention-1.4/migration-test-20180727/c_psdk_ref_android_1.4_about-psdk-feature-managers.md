---
description: null
seo-description: null
seo-title: Feature managers
title: Feature managers
uuid: c7af7b8c-8c06-4924-b655-3afddd893f38
index: n
internal: n
snippet: y
translate: y
---

# Feature managers

Feature managers provide a way for you to control individual features without traversing the entire  in search of code for one feature that could be scattered in multiple locations. Feature managers condense code into one class per feature. The feature managers wait for triggers from  events and then inform the class that uses the feature manager to handle the result. The feature manager provides the required information to the class. 
The feature managers perform the following tasks: 
* **Triggers  features. **These are function calls to trigger a  feature. For example, `PlaybackManager.play()` is called when the player application needs to start the video playback.
* **Listens to  events.** The feature manager needs to listen to  events to acquire information from the . For example, `AdsManager` listens to  Ads events to be notified when ad breaks start.
* **Dispatches events to the handler.**After the feature managers receive and process the events from the , they notify the client side to handle the event. For example, after `AdsManager` receives an ad break start event, it tells the player fragment to reflect this change in the UI (disable the scrub bar, show the ad overlay, etc.).

The Primetime reference implementation includes the following feature managers: 

| Feature manager |Default file |Feature |  |
|---|---|---|---|
| [Video playback](c_psdk_ref_video-playback.md)  |PlaybackManager |HLS playback and control, DVR playback and control, buffer control, and multi-bit rate handling. |Required |
| [DRM content protection](c_psdk_ref_content-protection.md)  |DrmManager |Content protection. |Required |
| [Ad insertion](c_psdk_ref_ad-insertion.md)  |AdsManager |Ad insertion, including , direct ad break, and custom ad break.  |Optional |
| [Closed captions](c_psdk_ref_closed-captions.md)  |CCManager |Closed captioning and VTT subtitles. |Optional |
| [Late-binding audio](c_psdk_ref_late-binding-audio.md)  |AAManager |Late binding audio. |Optional |
| [QoS](t_psdk_ref_qos-statistics.md)  |QosManager |QoS statistics. |Optional |
| Entitlement |EntitlementManager | entitlement integration.  |Optional |

The reference implementation contains basic default classes, listed above, and corresponding classes with the suffix of On. The default classes provide the default  behaviors while the classes with the On suffix include all the code required to trigger the  feature and listen to  events for that feature. 

* For optional features, the default code operates as if the feature is turned off.
* Classes with the On suffix operate as if the feature is turned on.

