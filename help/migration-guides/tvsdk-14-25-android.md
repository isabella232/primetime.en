---
title: TVSDK 1.4 to 2.5 for Android (Java)
seo-title: TVSDK 1.4 to 2.5 for Android (Java)
description: TVSDK 2.5 offers multiple benefits over version 1.4 in terms of performance, security, better integrations, and more.
seo-description: TVSDK 2.5 offers multiple benefits over version 1.4 in terms of performance, security, better integrations, and more.
uuid: aaab7aec-cb5b-4840-82e8-7112a8d98a8a
contentOwner: vishgupt
products: SG_PRIMETIME
topic-tags: migration
discoiquuid: 8d9136bf-b3ae-450c-bd8a-0bb246527886
index: y
internal: n
snippet: y
---

# TVSDK 1.4 to 2.5 for Android (Java) {#tvsdk-to-for-android-java}

TVSDK 2.5 offers multiple benefits over version 1.4 in terms of performance, security, better integrations, and more.

TVSDK solves the biggest challenges, on the device that matter the most. Android continues it’s global dominance, with over 86% of market share. Migration to TVSDK on Android will optimize playback performance to improve user engagement and accelerate time-to-market with support for new content formats.

## Benefits of migrating to TVSDK v2.5 {#benefits-of-migrating-to-tvsdk-v}

TVSDK 2.5 offers multiple benefits over version 1.4 in terms of performance, security, better integrations, and more. Read on to quickly know the benefits of migrating to this new version.

According to a third-party benchmarking study, v2.5 provides 5x reduction in startup time and 3.8x reduction in dropped frames over the industry average.

<table> 
 <caption>
   Table: Performance enhancements in v2.5 
 </caption> 
 <tbody> 
  <tr> 
   <td valign="top" width="336"><p><strong>Performance Features</strong></p> </td> 
   <td valign="top" width="336"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Instant-on for VOD and Live</p> </td> 
   <td valign="top" width="336"><p>Pre-load initial ts segments for Immediate playback for VOD and live-linear streams when channel switching, for a TV like experience.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Lazy ad loading</p> </td> 
   <td valign="top" width="336"><p>Starts playback as soon as pre-roll or content is available while resolving mid-roll ads in a parallel thread.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Persistent network connections</p> </td> 
   <td valign="top" width="336"><p>Increase in efficiency and decrease in latency of networking code for faster playback performance.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Improved ABR logic</p> </td> 
   <td valign="top" width="336"><p>The new ABR logic is based on buffer length, rate of change of buffer length, and measured bandwidth. This ensures that the ABR chooses the right bit rate when the bandwidth fluctuates and also optimizes the number of times the bitrate switch actually happens by monitoring the rate at which the buffer length changes.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Partial segment download</p> </td> 
   <td valign="top" width="336"><p>Starts playback as soon as enough frames from a segment are available for rendering video reliably on the client side.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Parallel downloads</p> </td> 
   <td valign="top" width="336"><p>TVSDK downloads audio and video segments in parallel for demuxed content to optimize playback performance.</p> </td> 
  </tr> 
 </tbody> 
</table>

The playback features improve consumer engagement by delivering the experience of linear broadcast on digital. Also, it helps you leverage native DRM such as Widevine for HD playback.

<table> 
 <caption>
   Table: Playback features in v2.5 
 </caption> 
 <tbody> 
  <tr> 
   <td valign="top" width="336"><p><strong>Playback Features</strong></p> </td> 
   <td valign="top" width="336"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>MP4 playback</p> </td> 
   <td valign="top" width="336"><p>MP4 short clips don’t have to be re-transcoded to playback within TVSDK.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>DASH VOD content playback</p> </td> 
   <td valign="top" width="336"><p>Basic DASH VOD playback use cases are supported.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Smooth Trickplay with ABR</p> </td> 
   <td valign="top" width="336"><p>Support for fast forward and rewind in HLS using keyframes at low rates and I-Frames at faster speeds. ABR support for all supported frames.</p> </td> 
  </tr> 
 </tbody> 
</table>

The features are important to meet the studio restrictions such as HD playback over native DRM.

<table> 
 <caption>
   Table: Content protection in v2.5 
 </caption> 
 <tbody> 
  <tr> 
   <td valign="top" width="336"><p><strong>Features</strong></p> </td> 
   <td valign="top" width="336"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Resolution Based Output Protection</p> </td> 
   <td valign="top" width="336"><p>playback can be restricted to only certain resolutions that are allowed by DRM requirements. Available only through Primetime DRM.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Widevine support</p> </td> 
   <td valign="top" width="336"><p>Supported with DASH VOD streams to enable native DRM use cases.</p> </td> 
  </tr> 
 </tbody> 
</table>

Direct billing enhancement does away with the need to create manual reports for billing every month. VHL 2.0 allows for a faster time to market with pre-build integration and better accuracy in tracking.

<table> 
 <caption>
   Table: Advertising, Analytics, and other workflow in v2.5 
 </caption> 
 <tbody> 
  <tr> 
   <td valign="top" width="336"><p><strong>Features</strong></p> </td> 
   <td valign="top" width="336"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Moat integration</p> </td> 
   <td valign="top" width="336"><p>Support for ad viewability measurement from Moat.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>VHL 2.0</p> </td> 
   <td valign="top" width="336"><p>The latest optimized video heartbeats library integration for automatic collection of usage data for Adobe Analytics.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Failover Support</p> </td> 
   <td valign="top" width="336"><p>Additional strategies implemented to continue uninterrupted playback, despite failures of host servers, playlist files, and segments.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>Direct Billing Integration</p> </td> 
   <td valign="top" width="336"><p>Sends billing metrics to Adobe Analytics backend which is certified by Adobe Primetime for streams used by customer.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>All the features of TVSDK v1.4 are supported in v2.5, except Multi-CDN support.

## Overview of the migration process {#overview-of-the-migration-process}

Migrating smoothly from TVSDK 1.4 to 2.5 entails changing to version 2.5 libraries, recompiling, then using this document to help debug any problems that occur.

TVSDK v1.4 libraries do not work with and coexist with v2.5 libraries. You must use v2.5 libraries with TVSDK 2.5 and migrate your applications and integrations to upgrade to TVSDK 2.5. This document describes how and what to change in your application code and how to address errors during re-compilation.

The psdk.jar file uses third party libraries for supporting different features. To prevent removal of the libraries, include the following in the `proguard.cfg` file:

```java
# Adobe TVSDK keep classes
-keep class com.adobe.** { *; }
-keep class com.google.android.exoplayer.**
{ *; }

```

In the `build.gradle` file, you need to include the compile directive to include the TVSDK based JAR files. If your app includes Adobe Video Analytics then you need to include the compile directive for the additional jars required for Adobe Video Analytics integration in the app

```java
# Compile Adobe TVSDK jars compile files('libs/psdk-va.jar')
compile files('libs/VideoHeartbeat.jar')

```

Multiple minor changes are not covered in this document. For the minor API changes, refer [TVSDK 2.5 for Android Java API](https://help.adobe.com/en_US/primetime/api/psdk/javadoc_2.5/index.html). The corresponding C++ API reference has detailed descriptions. For analogous C++ API documentation, see [TVSDK 2.5 for Android C++ API](https://help.adobe.com/en_US/primetime/api/psdk/cpp_2.5/index.html).

Multiple examples of the API usage are covered in the reference implementation distributed with the TVSDK.

## API changes in TVSDK v2.5 {#api-changes-in-tvsdk-v}

The new, obsolete, and modified APIs are documented below.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <caption>
   Table: API changes between TVSDK v1.4 and TVSDK v2.5 
 </caption> 
 <tbody> 
  <tr> 
   <td valign="top" width="224"><p><strong>TVSDK v1.4</strong></p> </td> 
   <td valign="top" width="224"><p><strong>TVSDK v2.5</strong></p> </td> 
   <td valign="top" width="224"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>import com.adobe.ave.drm</p> <p>.DRMAcquireLicenseSettings</p> </td> 
   <td valign="top" width="224"><p>import com.adobe.mediacore.drm</p> <p>.DRMAcquireLicenseSettings;</p> </td> 
   <td valign="top" width="224"><p>All class names in the TVSDK 2.5 API begin with the com.adobe.mediacore prefix. This is just an example.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>MediaPlayerException, IllegalStateException, or IllegalArgumentException</p> </td> 
   <td valign="top" width="224"><p>MediaPlayerException</p> </td> 
   <td valign="top" width="224"><p>In 2.5, the APIs generate only MediaPlayerException.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>MediaPlayer.PlayerState (MediaPlayer.Event.PLAYBACK)</p> </td> 
   <td valign="top" width="224"><p>MediaPlayerStatus (MediaPlayerEvent.STATUS_CHANGED)</p> </td> 
   <td valign="top" width="224"><p>In v2.5, MediaPlayer.PlayerState was renamed to a separate</p> <p>enum MediaPlayerStatus.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>DefaultMediaPlayer.create (getActivity().getApplicationContext())</p> </td> 
   <td valign="top" width="224"><p>MediaPlayer mediaPlayer =</p> <p>new MediaPlayer(getActivity(). getApplicationContext());</p> </td> 
   <td valign="top" width="224"><p>The static methods used to create objects are replaced by public constructors.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>MediaPlayer.seekToLocalTime()</p> </td> 
   <td valign="top" width="224"><p>MediaPlayer.seekToLocal()</p> </td> 
   <td valign="top" width="224"><p>The MediaPlayer.seekToLocalTime() method is now called MediaPlayer.seekToLocal().</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>closedCaptionsTrack.isActive()</p> </td> 
   <td valign="top" width="224"><p> </p> </td> 
   <td valign="top" width="224"><p>Not available</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>MetadataNode</p> </td> 
   <td valign="top" width="224"><p>Metadata</p> </td> 
   <td valign="top" width="224"><p>In v2.5, the Metadata class replaces the use of the</p> <p>v1.4 MetadataNode class.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>DefaultMetadataKeys</p> </td> 
   <td valign="top" width="224"><p>MetadataKeys</p> </td> 
   <td valign="top" width="224"><p>The DefaultMetadataKeys from v1.4 are in v2.5 enum MetadataKeys.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>AdvertisingFactory</p> </td> 
   <td valign="top" width="224"><p>ContentFactory</p> </td> 
   <td valign="top" width="224"><p>The AdvertisingFactory from v1.4 is renamed to ContentFactory in v2.5</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>PlacementOpportunityDetector</p> </td> 
   <td valign="top" width="224"><p>OpportunityGenerator</p> </td> 
   <td valign="top" width="224"><p>Detectors are replaced with Generators.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>mediaPlayer.getView().notifyClick();</p> </td> 
   <td valign="top" width="224"><p>mediaPlayer.notifyClick();</p> </td> 
   <td valign="top" width="224"><p>The notifyClick() method of MediaPlayerView was moved to the MediaPlayer class.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>public ABRControlParameters(ABRPolicy abrPolicy, int nInitialBitRate, int nMinBitRate, int nMaxBitRate)</p> </td> 
   <td valign="top" width="224"><p>public ABRControlParameters(int nInitialBitRate, int nMinBitRate, int nMaxBitRate, ABRPolicy abrPolicy, int nMinTrickPlayBitRate, int nMaxTrickPlayBitRate, int nMaxTrickPlayBandwidthUsage, double dMaxPlayoutRate)</p> </td> 
   <td valign="top" width="224"><p> </p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p>playbackInformation.getTimeToFirstFrame()</p> </td> 
   <td valign="top" width="224"><p> </p> </td> 
   <td valign="top" width="224"><p>Not available</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="224"><p> </p> </td> 
   <td valign="top" width="224"><p>playbackInformation.get<br /> PerceivedBandwidth()</p> </td> 
   <td valign="top" width="224"><p>TVSDK v2.5 QOSProvider has a new property to determine the perceived bandwidth during a streaming session.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Removed classes {#removed-classes}

The following classes are removed and have no equivalents.

* `TimeRangeCollection`
* `PSDKConfig`
* `BaseLogger`
* `DefaultLogger`
* `Log`
* `Logger`
* `LogFactory`
* `NullLogger`

The last six of these classes are available as utility classes in the reference implementation.

## Namespace changes {#namespace-changes}

The TVSDK 2.5 API consolidates namespaces.

All class names in the TVSDK 2.5 API begin with the com.adobe.mediacore prefix. Some class names in the TVSDK 1.4 API start with com.adobe.ave. The corresponding 2.5 classes change com.adobe.ave to com.adobe.mediacore. For example., note the changes in the following lines of code for 1.4 and 2.5:

```java
// TVSDK 1.4
import com.adobe.ave.drm.DRMAcquireLicenseSettings; import com.adobe.ave.drm.DRMLicense;
import com.adobe.ave.drm.DRMManager; import com.adobe.ave.drm.DRMMetadata

```

```java
// TVSDK 2.5
import com.adobe.mediacore.drm.DRMAcquireLicenseSettings; import com.adobe.mediacore.drm.DRMLicense;
import com.adobe.mediacore.drm.DRMManager; import com.adobe.mediacore.drm.DRMMetadata;

```

## Changes in event handling {#changes-in-event-handling}

To register events in this version, pass the handler to `addEventListener`. The list of events has been substantially revised from version 1.4 to version 2.5.  
For example, here is how to register an event handler for `MediaPlayerEvent.STATUS_CHANGED:`

```java
mPlayer.addEventListener(MediaPlayerEvent.STATUS_CHANGED,
new StatusChangeEventListener() {
@Override
public void onStatusChanged(MediaPlayerStatusChangeEvent event) {
//Handle status change event
}
});

```

This is how the event was registered in 1.4:

```java
mPlayer.addEventListener(MediaPlayer.Event.PLAYBACK, new MediaPlayer.PlaybackEventListener() {
@Override
public void onStateChanged(MediaPlayer.PlayerState state,
MediaPlayerNotification notification) {
//Handle status change event
}
// Additional handlers
...
});

```

The MediaPlayerEvent enum contains all event codes. The following event codes from 1.4 no longer exist in 2.5:

* `ADBREAK_PLACEMENT_COMPLETED`
* `ADBREAK_PLACEMENT_FAILED`
* `ADBREAK_REMOVAL_COMPLETED`
* `AD_BREAK_MANIFEST_LOAD_COMPLETE`
* `AD_MANIFEST_LOAD_COMPLETE`
* `AD_MANIFEST_LOAD_FAILED`
* `AUDIO_TRACK_FAILED`
* `BACKGROUND_MANIFEST_FAILED`
* `BUFFERING_FULL, CUSTOM_AD_EVENT`
* `CONTENT_MARKER`
* `CONTENT_PLACEMENT_COMPLETE`
* `CONTENT_CHANGED`
* `ITEM_REPLACED`
* `ITEM_READY`
* `VIEW_CLICKED`
* `PREPARED`
* `UPDATED`
* `OPPORTUNITY_COMPLETED`
* `OPPORTUNITY_CREATED`
* `OPPORTUNITY_FAILED`
* `PAUSE_AT_PERIOD_END`
* `PLAYBACK_STARTED`
* `PLAYBACK_PAUSED`
* `PLAYBACK_COMPLETED`
* `PLAY_COMPLETE`
* `POST_ROLL_COMPLETE`
* `RESOURCE_LOADED`
* `TIMED_METADATA_SKIPPED`
* `VIDEO_ERROR`
* `VIDEO_STATE_CHANGED`

The following event codes are new in 2.5:

* `AD_RESOLUTION_COMPLETE`
* `BUFFER_PREPARED`
* `CAPTIONS_UPDATED`
* `MANIFEST_UPDATED`
* `PLAYBACK_RANGE_UPDATED`
* `RESERVATION_REACHED`
* `TIME_CHANGED`
* `TIMED_EVENT`
* `TIMED_METADATA_ADDED_IN_BACKGROUND`

### Renamed Events {#renamed-events}

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="336"><p><strong>New Name</strong></p> </td> 
   <td valign="top" width="336"><p><strong>Old Name</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>SEEK_BEGIN</p> </td> 
   <td valign="top" width="336"><p>SEEK_STARTED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>SEEK_END</p> </td> 
   <td valign="top" width="336"><p>SEEK_COMPLETED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>SEEK_POSITION_ADJUSTED</p> </td> 
   <td valign="top" width="336"><p>SEEK_ADJUST_COMPLETED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>BUFFERING_BEGIN</p> </td> 
   <td valign="top" width="336"><p>BUFFERING_STARTED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>BUFFERING_END</p> </td> 
   <td valign="top" width="336"><p>BUFFERING_COMPLETED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>AUDIO_TRACK_UPDATED</p> </td> 
   <td valign="top" width="336"><p>AUDIO_TRACK_CHANGED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>STATUS_CHANGED</p> </td> 
   <td valign="top" width="336"><p>STATE_CHANGED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>TIMED_METADATA_AVAILABLE</p> </td> 
   <td valign="top" width="336"><p>TIMED_METADATA_ADDED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p>SIZE_AVAILABLE</p> </td> 
   <td valign="top" width="336"><p>SIZE_CHANGED</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="336"><p><a id="MediaPlayer_changes" name="MediaPlayer_changes"></a><a id="_bookmark6" name="_bookmark6"></a>LOAD_INFO</p> </td> 
   <td valign="top" width="336"><p>LOAD_INFORMATION_AVAILABLE</p> </td> 
  </tr> 
 </tbody> 
</table>

## MediaPlayer changes {#mediaplayer-changes}

A new way of constructing `MediaPlayer` and changes to some of the methods.

### Changes to the MediaPlayer class {#changes-to-the-mediaplayer-class}

Here are the changes to `MediaPlayer` class:

* The `MediaPlayerStatus` enum replaces `MediaPlayer.PlayerState`. For example:

```java
//TVSDK v1.4
mPlayer. addEventListener(MediaPlayer.Event.PLAYBACK, new MediaPlayer.PlaybackEventListener() {

@Override
public void onStateChanged(MediaPlayer.PlayerState state,MediaPlayerNotification notification) {
//Handle status change event
}
// Additional handlers
...
});

//TVSDK v2.5
mPlayer.addEventListener(MediaPlayerEvent.STATUS_CHANGED, new StatusChangeEventListener() {
@Override
public void onStatusChanged(MediaPlayerStatusChangeEvent event) {
//Handle status change event
}
//Additional handlers.
...
});

```

* The `MediaPlayer.seekToLocalTime()` method is now called `MediaPlayer.seekToLocal`. For example:

```java
//TVSDK v1.4
public void seekToLocal(long localPosition) { mediaPlayer.seekToLocalTime(localPosition);
}

//TVSDK v2.5
public void seekToLocal(long localPosition) { mediaPlayer.seekToLocal(localPosition);
}

```

* The `MediaPlayerView.notifyClick()` method is now `MediaPlayer.notifyClick()`. For example:

```java
//TVSDK v1.4
public void adClick() { mediaPlayer.getView().notifyClick();
}

//TVSDK v2.5
public void adClick() { mediaPlayer.notifyClick();
}

```

* The former `MediaPlayer.MediaPlayer.getNotificationHistory()` method is now gone and not replaced.
* The former `MediaPlayer.replaceCurrentItem()` is split into two methods: `replaceCurrentResource()`, which takes an instance of `MediaResource`, and `replaceCurrentItem()`, which takes an instance of `MediaPlayerItem`. For example:

```java
//TVSDK v1.4
MediaResource playerResource = MediaResource.createFromUrl(url, getAdvertisingMetadata());

mediaPlayer.replaceCurrentItem(playerResource);

//TVSDK v2.5 - replacing a resource
MediaResource playerResource = new MediaResource(url,
MediaResource.Type.HLS, getAdvertisingMetadata());
...
try {
mMediaPlayer.replaceCurrentResource(playerResource, _mediaPlayerItemConfig);
} catch (MediaPlayerException mediaPlayerException) {
// handle exception.
}
// TVSDK 2.5 - replacing an Item
MediaPlayerItemLoader itemLoader = new MediaPlayerItemLoader(context, new MediaPlayerItemLoader.LoaderListener() {

@Override
public void onError(PSDKErrorCode psdkErrorCode, String s) {
...
}
@Override
public void onLoadComplete(MediaPlayerItem mediaPlayerItem) {
...
}
@Override
public void onBufferingBegin() {
...
}
@Override
public void onBufferPrepared() {
...
}
});
MediaResource playerResource = new MediaResource(url,
MediaResource.Type.HLS, getAdvertisingMetadata());

itemLoader.load(playerResource); itemLoader.prepareBuffer();
mediaPlayer.replaceCurrentItem(itemLoader.getItem());

```

You can use this to switch between pre-initialized MediaPlayer instances, as in the case of blackouts.

#### Constructors replace static create() methods {#constructors-replace-static-create-methods}

You can use constructors in TVSDK v2.5, instead of using `create()` methods of TVSDK v1.4. All the classes with names beginning with Default, such as `DefaultMediaPlayer`, `DefaultNetworkConfig`, `DefaultContentFactory`, are not available in v2.5.

In some cases the TVSDK v1.4 API uses the following pattern for creating classes:

1. Define an interface (for example, `MediaPlayer`).
1. Provide a default class (for example, `DefaultMediaPlayer`).
1. Provide a `create()` method on the default class to supply a class that implements the interface.

In TVSDK v2.5, such interfaces are concrete classes and you create instances of these classes using the respective constructors. The following code snippets illustrate this difference:

```java
//TVSDK v1.4
// Create a media player
// MediaPlayer is an interface
private MediaPlayer createMediaPlayer() { MediaPlayer mediaPlayer =
DefaultMediaPlayer.create(getActivity().getApplicationContext()); return mediaPlayer;

//TVSDK v2.5
// Create a media player
// MediaPlayer is a class that you instantiate private MediaPlayer createMediaPlayer() {
MediaPlayer mediaPlayer =
new MediaPlayer(getActivity().getApplicationContext()); return mediaPlayer;
}
```

Other classes that don't follow this pattern but use `create()` methods in 1.4 include:

* MediaResource  
  This formerly used `MediaResource.createFromUrl()`. Now use the constructor, which takes a URL, resource type, and metadata. For example:

```java
//TVSDK v1.4
MediaResource playerResource = MediaResource.createFromUrl(url, getAdvertisingMetadata());
mediaPlayer.replaceCurrentItem(playerResource);

//TVSDK v2.5
MediaResource playerResource =
new MediaResource(url, MediaResource.Type.HLS, getAdvertisingMetadata());

try { mediaPlayer.replaceCurrentResource(playerResource,_mediaPlayerItemConfig);
} catch (MediaPlayerException mediaPlayerException) {
// handle exception.
}

```

* Ad
* AdAsset
* AdBreak

Some classes (for example, `ContentFactory`) are abstract classes with no publicly available default implementation (for example, `DefaultContentFactory`). In these cases you can provide a default implementation via a convenience function, for example: `mediaPlayerItemConfig.getDefaultContentFactory()`

#### Changes in closed captioning {#changes-in-closed-captioning}

The following changes affect classes related to closed captioning:

* When retrieving closed caption tracks, `MediaPlayerItem.getClosedCaptionTracks()` returns only active tracks.
* `ClosedCaptionTrack` no longer has an `isActive()` method.

```java
//TVSDK v1.4
public List<String> getClosedCaptionTracks(String label) {
List<String> closedCaptionsTracksAsStrings = new ArrayList<String>(); MediaPlayerItem currentItem = mediaPlayer.getCurrentItem(); List<ClosedCaptionsTrack> closedCaptionsTracks =
currentItem.getClosedCaptionsTracks(); Iterator<ClosedCaptionsTrack> iterator =
closedCaptionsTracks.iterator();
if (currentItem != null) {
while (iterator.hasNext()) {
ClosedCaptionsTrack closedCaptionsTrack = iterator.next(); String isActive = closedCaptionsTrack.isActive() ? " (" + label
+ ")" : "";
closedCaptionsTracksAsStrings.add(closedCaptionsTrack.getName()
+ " : " + closedCaptionsTrack.getLanguage() + isActive);
}
}
return closedCaptionsTracksAsStrings;
}

//TVSDK v2.5
public List<String> getClosedCaptionTracks(String label) {

MediaPlayerItem currentItem = mediaPlayer.getCurrentItem(); List<ClosedCaptionsTrack> closedCaptionsTracks =
currentItem.getClosedCaptionsTracks();
Iterator<ClosedCaptionsTrack> iterator = closedCaptionsTracks.iterator();

List<String> closedCaptionsTracksAsStrings = new ArrayList<String>(); if (currentItem != null) {
while (iterator.hasNext()) {
ClosedCaptionsTrack closedCaptionsTrack = iterator.next(); closedCaptionsTracksAsStrings.
add(closedCaptionsTrack.getName() + " : ");
}
}
return closedCaptionsTracksAsStrings;
}
// Add snippet and desc for CaptionsUpdatedEventListener mediaPlayer.addEventListener(MediaPlayerEvent.CAPTIONS_UPDATED,
captionsUpdatedEventListener);

private final CaptionsUpdatedEventListener captionsUpdatedEventListener = new CaptionsUpdatedEventListener() {

@Override
public void onCaptionsUpdated(MediaPlayerItemEvent mediaPlayerItemEvent) { getActivity().findViewById(R.id.sbPlayerControlCC).setVisibility(
View.VISIBLE/*Visible*/);
}
};
```

## Advertising changes {#advertising-changes}

There are several ad-related changes in version 2.5.

### Changes to advertising behavior {#changes-to-advertising-behavior}

The default behavior of the ad playback when a user performs a seek beyond an Ad pod changes slightly in v2.5. If the ad break is not watched then the ad is played back after a seek forward. When the app is using the default ad policy, the ad break is removed after playback is completed. Using TVSDK v2.5, if a user seeks behind an Ad pod on the timeline and the ad break is not watched, then no ad is played back.

However, in TVSDK v1.4, by default, an ad is played back in case of a seek backward. For example if you seek backward between the third and fourth ad break, the default behavior for TVSDK v1.4 is to play the third ad break.

### Ad Rules change {#ad-rules-change}

The Ad rules are specified using a JSON file. The format of the JSON file remains the same in both versions of the TVSDK. However, in TVSDK v2.5, the Ad rules JSON file must be hosted on a location accessible via a HTTP URL. The application can use an instance of AuditudeSettings.

```java
//TVSDK v2.5
AuditudeSettings result = new AuditudeSettings(); result.setCRSRulesJsonURL(<http url of AdobeTVSDKConfig.json>);

```

In TVSDK version 1.4, this file is placed below the assets folder in the application and TVSDK loads the file.

### Ad factory renaming {#ad-factory-renaming}

`AdvertisingFactory` is now named `ContentFactory`. With `ContentFactory` you can create customized advertising workflows by overriding some of its methods. Use return null to keep the default behaviors, as in the following:

```java
//TVSDK v2.5
new ContentFactory() {
@Override
public AdPolicySelector retrieveAdPolicySelector(MediaPlayerItem item) { return new CustomAdPolicySelector();
}
@Override
public List<OpportunityGenerator> retrieveGenerators(MediaPlayerItem item) { return null;
}
@Override
public List<ContentResolver> retrieveResolvers(MediaPlayerItem item) { return null;
}
@Override
public List<CustomAdHandler> retrieveCustomAdPlaybackHandlers(MediaPlayerItem item) { return null;
}
};
```

### Zero length Ad breaks {#zero-length-ad-breaks}

TVSDK 2.5 inserts zero length ad breaks as place holders when advertising server does not return any ads.

The zero length ad breaks can be determined by detecting the count of ads to be zero in the ad break using the onAdBreakStarted event and application has to handle these ad breaks accordingly.

### Metadata changes {#metadata-changes}

The Metadata class provides a more capable replacement for the former MetadataNode class.

* The Metadata class can store strings, byte arrays, and other Metadata objects:

```java
TVSDK v1.4
public AuditudeSettings createAdvertisementSettings() { Metadata advertisingParams = new MetadataNode();
advertisingParams.setValue("platform", Build.VERSION.RELEASE); advertisingParams.setValue("model", Build.MODEL);
AuditudeSettings adSettings = new AuditudeSettings();
// Set ad domain, zone id and media_id
...

// Set the target paramaters adSettings.setTargetingParameters(advertisingParams);

return adSettings;
}
//TVSDK v2.5
public AuditudeSettings createAdvertisementSettings() { Metadata advertisingParams = new Metadata();
advertisingParams.setValue("platform", Build.VERSION.RELEASE); advertisingParams.setValue("model", Build.MODEL);
AuditudeSettings adSettings = new AuditudeSettings();
// Set ad domain, zone id and media_id
...

// Set the target paramaters adSettings.setTargetingInfo(advertisingParams);

return adSettings;
}
```

* The `MetadataKeys` enum replaces `DefaultMetadataKeys`. Not all of the keys in `DefaultMetadataKeys` are present in the new version.

```java
//TVSDK v1.4
if (this.mediaPlayer != null && this.mediaPlayer.getCurrentItem() != null) { MetadataNode resourceMetadata =
(MetadataNode) this.mediaPlayer.getCurrentItem().getResource().getMetadata();
VideoAnalyticsMetadata vaMetadata = (VideoAnalyticsMetadata)
resourceMetadata.getNode(DefaultMetadataKeys.
VIDEO_ANALYTICS_METADATA_KEY.getValue());
}

//TVSDK v2.5
if (resourceMetadata.containsKey(VideoAnalyticsMetadata.
VIDEO_ANALYTICS_METADATA_KEY)) {
JSONObject vaMetadataObj =
new JSONObject(resourceMetadata.
getValue(VideoAnalyticsMetadata. VIDEO_ANALYTICS_METADATA_KEY));
vaMetadata = parseVideoAnalyticsMetadata(vaMetadataObj);
}

} catch (JSONException e) { e.printStackTrace();
}
```

* Advertising metadata is now represented by the `AdvertisingMetadata` class, a subclass of Metadata, and is now stored in `MediaPlayerItemConfig` rather than `MediaResource`.

```java
//TVSDK v1.4
MetadataNode mediaMetadata = new MetadataNode();

if (stream.live) { mediaMetadata.setNode(DefaultMetadataKeys.AUDITUDE_METADATA_KEY.getValue(),
getAdSettingsForLive());
} else {
mediaMetadata.setNode(DefaultMetadataKeys.AUDITUDE_METADATA_KEY.getValue(), getAdSettingsForVod());
}
MediaResource playerResource = MediaResource.createFromUrl(url, mediaMetadata);

//TVSDK v2.5
MediaPlayerItemConfig mediaItemConfig = new MediaPlayerItemConfig(context);

if (stream.live) {
AuditudeSettings adSettings = getAdSettingsForLive(); adSettings.setLivePreroll(true); mediaItemConfig.setAdvertisingMetadata(adSettings);
} else {
// Set the advertising parameters for VOD. mediaItemConfig.setAdvertisingMetadata(getAuditudeSettingsForVod());
}

// Create advertising metadata node Metadata mediaMetadata = new Metadata();

// Asset Url
MediaResource playerResource =
new MediaResource(url, MediaResource.Type.HLS, mediaMetadata);
try {
mediaPlayer.replaceCurrentResource(playerResource, mItemConfig);
} catch (MediaPlayerException mediaPlayerException) {
//handle exception.
}
```

Network configuration metadata, formerly a member of the `MediaResource` class, is now represented by the `NetworkConfiguration` class, and is now stored in `MediaPlayerItemConfig` rather than `MediaResource`.

```java
//TVSDK v1.4
MediaResource playerResource = MediaResource.createFromUrl(url, mediaMetadata);
...

//TVSDK v2.5
MediaPlayerItemConfig mediaItemConfig = new MediaPlayerItemConfig(context);

NetworkConfiguration mediaNetworkConfiguration = mediaItemConfig.getNetworkConfiguration();
```

### Changes to TimedMetadata parsing {#changes-to-timedmetadata-parsing}

The parsing of `TimedMetadata` has changed in 2.5 with respect to the datatypes for parsing ID3 tag.

```java
//TVSDK v1.4
public void onTimedMetadata(TimedMetadata timedMetadata) { TimedMetadata.Type type = timedMetadata.getType();
if (type.equals(TimedMetadata.Type.ID3)){ PMPDemoApp.logger.i(LOG_TAG + "#onTimedMetadata",
"New ID3 tag detected at time = " + timedMetadata.getTime());
Metadata metadata = timedMetadata.getMetadata(); Set<String> keys = metadata.keySet();
for (String key : keys) {
String value = metadata.getValue(key); PMPDemoApp.logger.i(LOG_TAG + "#onTimedMetadata",
"Key = " + key + " Value = " + value);
}
} else if (_mediaPlayer.getPlaybackRange() != null &&
_mediaPlayer.getPlaybackRange().getDuration() > 0) { displayRanges();
PMPDemoApp.logger.i(LOG_TAG +
"#onTimedMetadata",
"New timed metadata. Name " + timedMetadata.getName() +
", time " + timedMetadata.getTime() + ", id " + timedMetadata.getId() + ", metadata " +
timedMetadata.getMetadata() + ".");
/*if (!_timedMetadataList.contains(timedMetadata)) {
_timedMetadataList.add(timedMetadata);
}*/
/* scte35 */
if (timedMetadata.getName().equalsIgnoreCase("#EXT-OATCLS-SCTE35")) { parseSCTE35Tag(timedMetadata);
}
}
}

//TVSDK v2.5
public void onTimedMetadata(TimedMetadataEvent timedMetadataEvent) { PMPDemoApp.logger.i(LOG_TAG + " inside"," ontimedmetadata"); TimedMetadata timedMetadata = timedMetadataEvent.getTimedMetadata();

TimedMetadata.Type type = timedMetadata.getType(); if (type.equals(TimedMetadata.Type.ID3)) {
PMPDemoApp.logger.i(LOG_TAG +
"#onTimedMetadata",
"New ID3 tag detected at time = " + timedMetadata.getTime());
Metadata metadata = timedMetadata.getMetadata();
if (metadata != null) { PMPDemoApp.logger.i(LOG_TAG +
"::expandID3Metadata", "isEmpty " + metadata.isEmpty());
Set<String> keys = metadata.keySet(); PMPDemoApp.logger.i(LOG_TAG + "::expandID3Metadata",
"No of keys=" + keys.size());
String s;
for (String key : keys) {
byte[] value = metadata.getByteArray(key); s = new String(value);
if (key.equalsIgnoreCase("APIC"))
s = "SUPPRESSING BINARY DATA FOR ATTACHED PICTURE.";
PMPDemoApp.logger.i(LOG_TAG + "::expandID3Metadata",
"Key=" + key + ", Length=" + value.length + ", Value=" + s.trim());
}
}
} else if (_mediaPlayer.getPlaybackRange() != null &&
_mediaPlayer.getPlaybackRange().getDuration() > 0) { displayRanges();
PMPDemoApp.logger.i(LOG_TAG +
"#onTimedMetadata",
"New timed metadata. Name " + timedMetadata.getName() +
", time " + timedMetadata.getTime() + ", id " + timedMetadata.getId() + ", metadata " +
timedMetadata.getMetadata() + ".");
/*if (!_timedMetadataList.contains(timedMetadata)) {
_timedMetadataList.add(timedMetadata);
}*/
/* scte35 */
if (timedMetadata.getName().equalsIgnoreCase("#EXT-OATCLS-SCTE35")) { PMPDemoApp.logger.i(LOG_TAG +
" inside ontimedmetadata"," ext"); parseSCTE35Tag(timedMetadata);
}
}
}
```

### Other changes {#other-changes}

The following additional changes are available in version 2.5:

* The `notifyClick()` method has moved from `MediaPlayerView` to `MediaPlayer`.

* `AdPolicySelector` is an interface, not a class. Implement all its methods.
* `AdPolicyInfo` now contains a list of `AdBreakTimelineItem`, not `AdBreakPlacement`.

* API name of `ContentResolver` abstract class is changed.
* `PlacementOpportunityDetector` is no longer available. Instead, extend the `OpportunityGenerator` abstract class. The reference implementation provides an example of this.

* The parameters of the `AdBreakPlacement` constructor are the same, but in a different order. For a sample implementation, see the Reference Player implementation bundled with the product.

## Changes in DRM {#changes-in-drm}

The majority of changes in this version are in the DRM layer. The following table shows additional changes between versions 1.4 and 2.5:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="168"><p><strong>DRMManager Method</strong></p> </td> 
   <td valign="top" width="168"><p><strong>Success Callback in 1.4</strong></p> </td> 
   <td valign="top" width="168"><p><strong>Error Callback in 1.4</strong></p> </td> 
   <td valign="top" width="168"><p><strong>Listener in 2.5</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">acquireLicense</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMLicenseAcquiredCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMAcquireLicenseListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">acquirePreviewLicense</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMLicenseAcquiredCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMAcquireLicenseListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">authenticate</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMAuthenticationCompleteCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMAuthenticateListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">createMetadataFromBytes</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">NA</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMErrorListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">initialize</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">joinLicenseDomain</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">leaveLicenseDomain</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">resetDRM</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">returnLicense</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMLicenseReturnCompleteCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMReturnLicenseListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">setAuthenticationToken</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteListener</span></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="168"><p><span class="code">storeLicenseBytes</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationErrorCallback</span></p> </td> 
   <td valign="top" width="168"><p><span class="code">DRMOperationCompleteListener</span></p> </td> 
  </tr> 
 </tbody> 
</table>

```java
//TVSDK 1.4
private final MediaPlayer.DRMEventListener _drmEventListener = new MediaPlayer.DRMEventListener() {

@Override
public void onDRMMetadata(final DRMMetadataInfo drmMetadataInfo) { PMPDemoApp.logger.i(LOG_TAG + "::MediaPlayer.DRMEventListener#onDRMMetadata",
"DRM metadata available: " + drmMetadataInfo + ".");
if (getSuppressAutoPlayPreference() && drmMetadataInfo != null) {
// if suppress play setting, then the user is a tester who
// wishes to manually intervene between the metadata available
// event and the play event, so launch the metadata interface
// and give it the loaded metadata bytes, but only once
_drmMetadata = drmMetadataInfo.getDRMMetadata();
}
if (drmMetadataInfo == null ||
!DRMHelper.isAuthNeeded(drmMetadataInfo.getDRMMetadata())) { PMPDemoApp.logger.i(LOG_TAG + "#onDRMMetadata", "DRM auth is not needed."); return;
}
// Perform DRM auth.
// Possible logic might take into consideration a threshold
// between the current player time and the DRM metadata start
// time. For the time being, we resolve it as soon as we receive
// the DRM metadata.

DRMManager drmManager = _mediaPlayer.getDRMManager(); if (drmManager == null) {
PMPDemoApp.logger.e(LOG_TAG + "#onDRMMetadata", "DRMManager is null."); return;
}
SharedPreferences sharedPreferences =
PreferenceManager.getDefaultSharedPreferences(getActivity()); String authUser =
sharedPreferences.getString(PMPDemoApp.SETTINGS_DRM_USERNAME,
getResources().getString(R.string.drmUsername));
String authPass = sharedPreferences.getString(PMPDemoApp.SETTINGS_DRM_PASSWORD,
getResources().getString(R.string.drmPassword));
DRMHelper.performDrmAuthentication(drmManager,
drmMetadataInfo.getDRMMetadata(), authUser,
authPass,
new DRMAuthenticationListener() {
@Override
public void onAuthenticationStart() { PMPDemoApp.logger.i(LOG_TAG + "#onAuthenticationStart",
"DRM authentication started for DRM metadata at [" + drmMetadataInfo.getPrefetchTimestamp() + "].");
}
@Override
public void onAuthenticationError(long majorCode,
long minorCode, Exception e) {
if (getActivity() == null) { return;
}
PMPDemoApp.logger.e(LOG_TAG +
"#onAuthenticationError",
"DRM authentication failed. " + majorCode + " 0x" + Long.toHexString(minorCode));
_handler.post(new Runnable() {
@Override
public void run() { showToast(getString(R.string.drmAuthenticationError)); getActivity().finish();
}
});
}
@Override
public void onAuthenticationComplete(byte[] authenticationToken) { PMPDemoApp.logger.i(LOG_TAG +
"#onAuthenticationComplete",
"Auth successful for DRM metadata at [" + drmMetadataInfo.getPrefetchTimestamp() + "].");
}
});
}
};

//TVSDK 2.5
private final DRMMetadataInfoEventListener drmMetadataInfoEventListener = new DRMMetadataInfoEventListener() {
@Override
public void onDRMMetadataInfo(DRMMetadataInfoEvent drmMetadataInfoEvent) { final DRMMetadataInfo drmMetadataInfo =
drmMetadataInfoEvent.getDRMMetadataInfo();
PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.DRMEventListener#onDRMMetadata",
"DRM metadata available: " + drmMetadataInfo + ".");
if (getSuppressAutoPlayPreference() && drmMetadataInfo != null) {
// if suppress play setting, then the user is a tester who
// wishes to manually intervene between the metadata
// available event and the play event, so launch the
// metadata interface and give it the loaded metadata
// bytes, but only once
drmMetadata = drmMetadataInfo.getDRMMetadata();
}
if (drmMetadataInfo ==
null || !DRMHelper.isAuthNeeded(drmMetadataInfo.getDRMMetadata())) { PMPDemoApp.logger.i(LOG_TAG +
"#onDRMMetadata",
"DRM auth is not needed.");
return;
}
// Perform DRM auth.
// Possible logic might take into consideration a threshold between
// the current player time and the DRM metadata start time. For the
// time being, we resolve it as soon as we receive the DRM metadata.

DRMManager drmManager = _mediaPlayer.getDRMManager(); if (drmManager == null) {
PMPDemoApp.logger.e(LOG_TAG +
"#onDRMMetadata", "DRMManager is null.");
return;
}

SharedPreferences sharedPreferences = PreferenceManager.getDefaultSharedPreferences(getActivity());
String authUser = sharedPreferences.getString(PMPDemoApp.SETTINGS_DRM_USERNAME,
getResources().getString(R.string.drmUsername));
String authPass = sharedPreferences.getString(PMPDemoApp.SETTINGS_DRM_PASSWORD,
getResources().getString(R.string.drmPassword));
DRMHelper.performDrmAuthentication(drmManager,
drmMetadataInfo.getDRMMetadata(), authUser,
authPass,
new DRMAuthenticationListener() {
@Override
public void onAuthenticationStart() { PMPDemoApp.logger.i(LOG_TAG +
"#onAuthenticationStart",
"DRM authentication started for DRM metadata at [" + drmMetadataInfo.getPrefetchTimestamp() + "].");
}
@Override
public void onAuthenticationError(int major,
int minor,
String erroString, String serverErrorURL) {
if (getActivity() == null) { return;
}
PMPDemoApp.logger.e(LOG_TAG +
"#onAuthenticationError",
"DRM authentication failed. " + major +
" 0x" +
Long.toHexString(minor));
_handler.post(new Runnable() {
@Override
public void run() { showToast(getString(R.string.drmAuthenticationError)); getActivity().finish();
}
});
}
@Override
public void onAuthenticationComplete(byte[] authenticationToken) { PMPDemoApp.logger.i(LOG_TAG +
"#onAuthenticationComplete",
"Auth successful for DRM metadata at [" + drmMetadataInfo.getPrefetchTimestamp() + "].");
}
});
}
};
```

The static `DRMManager` instance that was available in 1.4 after mediaplayer is created is now available after the `onDRMMetadataInfo` event listener is triggered.

## Adaptive Bitrate (ABR) related changes {#adaptive-bitrate-abr-related-changes}

### Changes in constants {#changes-in-constants}

Many constants have changed type from `String` to `int`. For example: `MediaResourceType`, `ABRControlParameters`, and `MediaPlayerStatusChangeEvent`.

```java
//TVSDK v1.4
ABRControlParameters
private void setAbrControlParams() { SharedPreferences sharedPreferences =
PreferenceManager.getDefaultSharedPreferences(getActivity());
if (sharedPreferences.getBoolean(PMPDemoApp.SETTINGS_ABR_CTRL_ENABLED,
PMPDemoApp.DEFAULT_ABR_ENABLED)) {
int initialBitRate = getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_INITIAL_BITRATE, 0);
int minBitRate = getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_MIN_BITRATE, 0);
int maxBitRate = getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_MAX_BITRATE, PMPDemoApp.DEFAULT_MAX_BIT_RATE);
int mbrPolicyAsInt =
getIntPreference(sharedPreferences, PMPDemoApp.SETTINGS_ABR_POLICY, 0); ABRControlParameters.ABRPolicy abrPolicy = policyFromInt(mbrPolicyAsInt); abrPolicy = abrPolicy != null ?
abrPolicy : ABRControlParameters.ABRPolicy.ABR_MODERATE;
_mediaPlayer.setABRControlParameters(new ABRControlParameters(initialBitRate,
minBitRate, maxBitRate, abrPolicy));
}
}

//TVSDK v2.5
ABRControlParameters
private void setAbrControlParams() { ABRControlParametersBuilder abrBuilder =
new ABRControlParametersBuilder();

if (sharedPreferences.getBoolean(PMPDemoApp.SETTINGS_ABR_CTRL_ENABLED, PMPDemoApp.DEFAULT_ABR_ENABLED)) {

abrBuilder.setInitialBitRate(getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_INITIAL_BITRATE,
ABRControlParameters.DEFAULT_ABR_INITIAL_BITRATE)); abrBuilder.setMinBitRate(getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_MIN_BITRATE,
ABRControlParameters.DEFAULT_ABR_MIN_BITRATE)); abrBuilder.setMaxBitRate(getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_MAX_BITRATE,
ABRControlParameters.DEFAULT_ABR_MAX_BITRATE)); abrBuilder.setMaxPlayoutRate(getDoublePreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_MAX_PLAYOUT_RATE,
ABRControlParameters.DEFAULT_MAX_PLAYOUT_RATE)); abrBuilder.setMinTrickPlayBitRate(getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_MIN_TRICKPLAY_BITRATE,
ABRControlParameters.DEFAULT_ABR_MIN_BITRATE)); abrBuilder.setMaxTrickPlayBitRate(getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_MAX_TRICKPLAY_BITRATE,
ABRControlParameters.DEFAULT_ABR_MAX_BITRATE)); abrBuilder.setMaxTrickPlayBandwidthUsage(getIntPreference(sharedPreferences,
PMPDemoApp.SETTINGS_ABR_MAX_TRICKPLAY_BANDWIDTH,
ABRControlParameters.DEFAULT_ABR_MAX_BITRATE));

switch (getIntPreference(sharedPreferences, PMPDemoApp.SETTINGS_ABR_POLICY, -1)) {
case 0: abrBuilder.setPolicy(ABRControlParameters.ABRPolicy.ABR_CONSERVATIVE); break;
case 1: abrBuilder.setPolicy(ABRControlParameters.ABRPolicy.ABR_MODERATE); break;
case 2: abrBuilder.setPolicy(ABRControlParameters.ABRPolicy.ABR_AGGRESSIVE); break;
default: abrBuilder.setPolicy(ABRControlParameters.DEFAULT_ABR_POLICY);
}
}
_mediaPlayer.setABRControlParameters(abrBuilder.toABRControlParameters());
}
```

### Changes to the ABRControlParameters constructor {#changes-to-the-abrcontrolparameters-constructor}

Some parameters have been added, some renamed, and some moved. The following are the constructor signature in v1.4 and the new signature in 2.5:

```java
//TVSDK v1.4
public ABRControlParameters(ABRPolicy abrPolicy,
int nInitialBitRate, int nMinBitRate,
int nMaxBitRate)

//TVSDK v2.5
public ABRControlParameters(int nInitialBitRate,
int nMinBitRate, int nMaxBitRate,
ABRPolicy abrPolicy,
int nMinTrickPlayBitRate, int nMaxTrickPlayBitRate,
int nMaxTrickPlayBandwidthUsage, double dMaxPlayoutRate)
```

## Error events and handling {#error-events-and-handling}

### Changes in error handling {#changes-in-error-handling}

The `MediaError` class has been replaced with the `Notification` class. The only difference between the classes `MediaError` and `Notification` is that the latter does not contain a description attribute. The TVSDK 1.4 error codes with values 101xxx, 102xxx,104xxx,106xxx,107xxx,109xxx do not exist in TVSDK 2.5. For the playback codes in TVSDK 2.5, see [Native Error- video playback values](assets/psdk_android_2.5.pdf).

The following are examples of error handling in TVSDK 1.4 and 2.5:

```java
//TVSDK v1.4
@Override
public void onStateChanged(MediaPlayer.PlayerState state, MediaPlayerNotification notification) {
PMPDemoApp.logger.i(LOG_TAG + "::MediaPlayer.PlayerStateEventListener#onStateChanged()", "Player state changed to [" + state
+ "].");

switch (state) {
// Non recoverable state - either reset player and reinitialize
// or release the player and create a new one.
case ERROR: PMPDemoApp.logger.e(LOG_TAG +
"::MediaPlayer.PlayerStateEventListener#onStateChanged()", "Error: " + notification + "."); getActivity().finish();
break;
default:
// do nothing
}
}

//TVSDK v2.5
private final StatusChangeEventListener statusChangeEventListener = new StatusChangeEventListener() {
@Override
public void onStatusChanged(MediaPlayerStatusChangeEvent mediaPlayerStatusChangeEvent)
{
MediaPlayerStatus state = mediaPlayerStatusChangeEvent.getStatus(); PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.PlayerStateEventListener#onStateChanged()", "Player state changed to [" + state
+ "].");
switch (state) {
// Non recoverable state - either reset player and reinitialize
// or release the player and create a new one.
case ERROR:
PMPDemoApp.logger.e(LOG_TAG + "::MediaPlayer.PlayerStateEventListener#onStateChanged()", "Error: ");
printErrorMetadata(mediaPlayerStatusChangeEvent.getMetadata()); showToast("MediaPlayer status ERROR: Look at the logs for details"); getActivity().finish();
break;
default:
// do nothing
}
}
};
```

All the recoverable errors are treated as warnings and are handled using the `NotificationEventListener` in TVSDK 2.5. The warnings appear as notifications with the `onOperationFailed` Listener in the QOS handler in TVSDK 1.4 where as in TVSDK 2.5 the Notification is separate event. The warning handled in 1.4 and 2.5 is as follows:

```java
//TVSDK v1.4
private final MediaPlayer.QOSEventListener _qosEventListener = new MediaPlayer.QOSEventListener()
{
@Override
public void onBufferStart() {
PMPDemoApp.logger.i(LOG_TAG + "::MediaPlayer.QOSEventListener#onBufferStart()", "Buffering started.");
}
@Override
public void onBufferComplete() {
PMPDemoApp.logger.i(LOG_TAG + "::MediaPlayer.QOSEventListener#onBufferComplete()", "Buffering complete.");
}
@Override
public void onSeekStart() {
PMPDemoApp.logger.i(LOG_TAG + "::MediaPlayer.QOSEventListener#onSeekStart()", "Seek starting.");
}
@Override
public void onSeekComplete(long adjustedTime) {
PMPDemoApp.logger.i(LOG_TAG + "::MediaPlayer.QOSEventListener#onSeekComplete()", "Seek complete at position: " + adjustedTime + ".");
}
@Override
public void onLoadInfo(LoadInfo loadInfo) {
PMPDemoApp.logger.i(LOG_TAG + "::MediaPlayer.QOSEventListener#onLoadInfo()", "Url: " + loadInfo.getUrl() + ", size: "
+ loadInfo.getSize() + " bytes, media duration: " + loadInfo.getMediaDuration() + "ms, download duration: " + loadInfo.getDownloadDuration() + "ms");
}
@Override
public void onOperationFailed(MediaPlayerNotification.Warning warning) {

StringBuffer sb = new StringBuffer("Player operation failed: "); sb.append(warning.getCode()).append(" - ").append(warning.getDescription()); if (warning.getMetadata() != null) {
sb.append("Warning metadata: ").append(warning.getMetadata().toString());
}

MediaPlayerNotification innerNotification = warning.getInnerNotification(); registerFailedAudioTrackIndex(innerNotification); handleFailedSeekEvent(innerNotification);

while (innerNotification != null) { sb.append("Inner notification: ");
sb.append(innerNotification.getCode()).append(" - ").append(innerNotification.getDescription());
Metadata metadata = innerNotification.getMetadata(); if (metadata != null) {
for (String key : metadata.keySet()) { sb.append(" - ").append

//TVSDK v2.5
private final NotificationEventListener notificationEventListener = new NotificationEventListener() {
/**
* An example of dumping the information within a Notification. Here, we don't handle the event in
* any way except to print a log message.
* @param event The NotificationEvent
*/
@Override
public void onNotification(NotificationEvent event) { Notification notification = event.getNotification(); Notification.Type type = notification.getType(); StringBuilder sb = new StringBuilder(); sb.append("[").append(type).append("]");
sb.append(" Player operation failed (").append(notification.getCode()).append(")"); Metadata metadata = notification.getMetadata();
if (metadata != null)
{
for (String key : metadata.keySet())
{
sb.append(", ").append(key).append(" = ").append(metadata.getValue(key));
}
}
Notification inner = notification.getInnerNotification(); if (inner != null) {
sb.append(" :: Inner Notification [").append(inner.getType()).append("](").append(inner.getCode()).append(")");
Metadata innerMetadata = inner.getMetadata(); if (innerMetadata != null) {
for (String iKey : innerMetadata.keySet()) { sb.append(", ").append(iKey).append(" =
").append(innerMetadata.getValue(iKey));
}
}
}
switch(type)
{
case ERROR:
PMPDemoApp.logger.e(LOG_TAG, sb.toString()); break;
case WARNING:
PMPDemoApp.logger.w(LOG_TAG, sb.toString()); break;
default:
PMPDemoApp.logger.i(LOG_TAG, sb.toString()); break;
}
showToast(sb.toString()); PMPDemoApp.logger.d(LOG_TAG, sb.toString());
}
};
```

### New exceptions {#new-exceptions}

While TVSDK v1.4 used a combination of nulls, error returns, and a variety of exceptions ( `MediaPlayerException`, `IllegalStateException`, and `IllegalArgumentException`), TVSDK v2.5 `generatesMediaPlayerException` for all errors.

>[!NOTE]
>
>To get details on a MediaPlayerException, you can use `getErrorCode()`.

An example of the change is below:

```java
//TVSDK v1.4
public void setBufferControlParams() { try {
mediaPlayer.setBufferControlParameters(getBufferParamsFromSettings());
} catch (IllegalArgumentException e) { PrimetimeReference.logger.w(LOG_TAG +
"#setBufferControlParams",
"Unable to apply buffering params: " + e.getMessage() + ".");
}
}

//TVSDK v2.5
public void setBufferControlParams() { try {
mediaPlayer.setBufferControlParameters(getBufferParamsFromSettings());
} catch (MediaPlayerException e) { PrimetimeReference.logger.w(LOG_TAG + "#setBufferControlParams", "Unable to apply buffering params: " + e.getMessage() + ".");
}
}
```

## Changes to QOS parameters {#changes-to-qos-parameters}

There are minor changes to QOSProvider object properties:

* The `TimeToFirstFrame` is not available in TVSDK 2.5.
* TVSDK 2.5 QOSProvider has a new property to determine the perceived bandwidth during a streaming session.

```java
//TVSDK v1.4
public void updateQosInformation(PlaybackInformation playbackInformation) { if (playbackInformation == null) {
return;
}
setQosItem("Frame rate", (int) playbackInformation.getFrameRate() +
" (" + (int) playbackInformation.getDroppedFrameCount() + " dropped)"); setQosItem("Bitrate", (int) playbackInformation.getBitrate()); setQosItem("Buffering time", (long) playbackInformation.getBufferingTime()); setQosItem("Buffer length", (long) playbackInformation.getBufferLength()); setQosItem("Buffer time", (long) playbackInformation.getBufferTime()); setQosItem("Empty buffer count", (int) playbackInformation.getEmptyBufferCount()); setQosItem("Time to load", (int) playbackInformation.getTimeToLoad()); setQosItem("Time to start", (int) playbackInformation.getTimeToStart()); setQosItem("Time to first frame", (int) playbackInformation.getTimeToFirstFrame()); setQosItem("Time to prepare", (int) playbackInformation.getTimeToPrepare()); setQosItem("Last seek time", (int) playbackInformation.getLastSeekTime());
}

//TVSDK v2.5
public void updateQosInformation(PlaybackInformation playbackInformation) { if (playbackInformation == null) {
return;
}
setQosItem("Frame rate", (int) playbackInformation.getFrameRate() +
" (" + (int) playbackInformation.getDroppedFrameCount() + " dropped)"); setQosItem("Bitrate", (int) playbackInformation.getBitRate()); setQosItem("Buffering time", (long) playbackInformation.getBufferingTime()); setQosItem("Buffer length", (long) playbackInformation.getBufferLength()); setQosItem("Buffer time", (long) playbackInformation.getBufferTime()); setQosItem("Empty buffer count", (int) playbackInformation.getEmptyBufferCount()); setQosItem("Time to load", (int) playbackInformation.getTimeToLoad()); setQosItem("Time to start", (int) playbackInformation.getTimeToStart());
setQosItem("Time to prepare", (int) playbackInformation.getTimeToPrepare());
setQosItem("Perceived Bandwidth", (int) playbackInformation.getPerceivedBandwidth());
```

* The `QOSEventListener::onOperationFailed()` no longer exists in TVSDK 2.5. The warnings that used to appear in this event listener will now appear in the `NotificationEventListener::onNotification()` event listener.

* The `QOSProvider event listeners onBufferStart()`, `onBufferComplete()`, `onSeekStart()`, `onSeekComplete()`, and `onLoadInfo()` are individual event listeners that are bound with a mediaPlayer instance.

```java
//TVSDK v1.4
private final MediaPlayer.QOSEventListener _qosEventListener = new MediaPlayer.QOSEventListener() {

@Override
public void onBufferStart() { PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onBufferStart()", "Buffering started.");
showBufferingSpinner();
}
@Override
public void onBufferComplete() { PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onBufferComplete()", "Buffering complete.");
hideBufferingSpinner();
}
@Override
public void onSeekStart() { PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onSeekStart()", "Seek starting.");
inTrickPlayMode = false;
}
@Override
public void onSeekComplete(long adjustedTime) { PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onSeekComplete()", "Seek complete at position: " +
adjustedTime + ".");
_controlBar.setPosition(adjustedTime);
if (adjustedTime == _mediaPlayer.getPlaybackRange().getEnd() &&
_mediaPlayer.getStatus() == MediaPlayer.PlayerState.COMPLETE) {
// Show the replay button. showReplayButton();
}
if (_mediaPlayer.getStatus() == MediaPlayer.PlayerState.PAUSED) {
// Show the pause icon.
_controlBar.pause();
}
}
@Override
public void onLoadInfo(LoadInfo loadInfo) { PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onLoadInfo()", "Url: " +
loadInfo.getUrl() + ", size: " + loadInfo.getSize() +
" bytes, media duration: " +
loadInfo.getMediaDuration() + "ms, download duration: " +
loadInfo.getDownloadDuration() + "ms");
 
public void onOperationFailed(MediaPlayerNotification.Warning warning) {

StringBuffer sb = new StringBuffer("Player operation failed: "); sb.append(warning.getCode()).append(" - ").append(warning.getDescription()); if (warning.getMetadata() != null) {
sb.append("Warning metadata: ").append(warning.getMetadata().toString());
}

MediaPlayerNotification innerNotification = warning.getInnerNotification(); registerFailedAudioTrackIndex(innerNotification); handleFailedSeekEvent(innerNotification);

while (innerNotification != null) { sb.append("Inner notification: ");
sb.append(innerNotification.getCode()).append(" - "). append(innerNotification.getDescription());
Metadata metadata = innerNotification.getMetadata(); if (metadata != null) {
for (String key : metadata.keySet()) { sb.append(" - ").append(key).append(": ").
append(metadata.getValue(key));
}
}
innerNotification = innerNotification.getInnerNotification();
}
String errMsg = sb.toString(); PMPDemoApp.logger.w(LOG_TAG +
"::MediaPlayer.QOSEventListener#onOperationFailed()", errMsg);
showToast(errMsg);
}
};

//TVSDK v2.5
mediaPlayer.addEventListener(MediaPlayerEvent.LOAD_INFORMATION_AVAILABLE,
loadInfoEventListener); mediaPlayer.addEventListener(MediaPlayerEvent.BUFFERING_BEGIN,
bufferingBeginEventListener); mediaPlayer.addEventListener(MediaPlayerEvent.BUFFERING_END,
bufferingEndEventListener); mediaPlayer.addEventListener(MediaPlayerEvent.SEEK_BEGIN,
seekBeginEventListener); mediaPlayer.addEventListener(MediaPlayerEvent.SEEK_END,
seekEndEventListener);
// Buffering events.
BufferingBeginEventListener bufferingBeginEventListener = new BufferingBeginEventListener() {
@Override
public void onBufferingBegin(BufferEvent bufferEvent) { PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onBufferStart()", "Buffering started.");
showBufferingSpinner();
}
};

BufferingEndEventListener bufferingEndEventListener = new BufferingEndEventListener() {
@Override
public void onBufferingEnd(BufferEvent bufferEvent) { PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onBufferComplete()",
"Buffering complete."); hideBufferingSpinner();
}
};

BufferPreparedEventListener bufferPreparedEventListener = new BufferPreparedEventListener() {
@Override
public void onBufferPrepared() {
}
};
// seek events.
SeekBeginEventListener seekBeginEventListener = new SeekBeginEventListener() {

@Override
public void onSeekBegin(SeekEvent seekEvent) { PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onSeekStart()", "Seek starting.");
inTrickPlayMode = false;
}
};
SeekEndEventListener seekEndEventListener = new SeekEndEventListener() {
@Override
public void onSeekEnd(SeekEvent seekEvent) {
double adjustedTime = seekEvent.getActualPosition();
PMPDemoApp.logger.i(LOG_TAG +
"::MediaPlayer.QOSEventListener#onSeekComplete()", "Seek complete at position: " + adjustedTime + ".");
_controlBar.setPosition((long) adjustedTime);
if (adjustedTime == _mediaPlayer.getPlaybackRange().getEnd() &&
_mediaPlayer.getStatus() == MediaPlayerStatus.COMPLETE) {
// Show the replay button. showReplayButton();
}
if (_mediaPlayer.getStatus() == MediaPlayerStatus.PAUSED) {
// Show the pause icon.
_controlBar.pause();
}
}
};
/**
* LoadInformationEventListener that intercepts PSDK load info events
*/
private final LoadInformationEventListener loadInfoEventListener = new LoadInformationEventListener() {

@Override
public void onLoadInformation(LoadInformationEvent event) { LoadInformation loadInfo = event.getLoadInfomation(); PMPDemoApp.logger.i(
LOG_TAG + "::LoadInformationEventListener#onLoadInfomation()", "Url: " + loadInfo.getUrl() + ", size: "
+ loadInfo.getSize()
+ " bytes, download duration: "
+ loadInfo.getDownloadDuration() + "ms");
}
};
```

