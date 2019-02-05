---
description: Licensing and playback of FairPlay-protected content requires swapping of URL schemes, between the scheme used in the video manifest file (skd ) and the one used in ExpressPlay token requests (https ).
seo-description: Licensing and playback of FairPlay-protected content requires swapping of URL schemes, between the scheme used in the video manifest file (skd ) and the one used in ExpressPlay token requests (https ).
seo-title: Licensing and playback for FairPlay
title: Licensing and playback for FairPlay
uuid: 8b37bf3b-ba9f-42b3-bbb3-1c089f86ed5c
---

# Licensing and playback for FairPlay {#licensing-and-playback-for-fairplay}

Licensing and playback of FairPlay-protected content requires swapping of URL schemes, between the scheme used in the video manifest file (skd:) and the one used in ExpressPlay token requests (https:).

Instructions for implementing licensing and playback from an iOS TVSDK client are here: [Enable Apple FairPlay in TVSDK applications](https://help.adobe.com/en_US/primetime/psdk/ios/index.html#PSDKs-task-Enable_Apple_FairPlay_in_TVSDK_applications). You can also optionally implement offline playback and license rotation for FairPlay.

## HLS Offline with FairPlay {#section_047A05D1E3B64883858BC601CFC8F759}

You may want to make it possible for users to play FairPlay-protected content when its licensing is not retrievable because the player is isolated from the web (such as on an airplane).

Before you begin this task, download and read the Apple document **"Offline Playback with FairPlay Streaming and HTTP Live Streaming"**. Read the guide to learn how to download Transport Stream (TS) segments and save them to your local machine.

Implement offline play for FairPlay with this workflow:

1. Download the HLS TS segment. 
1. Request Persistent Rental license from the FairPlay server (see **"FairPlay Persistent Rental Policy"**). 
1. Save the `persistentContentKey`. 
1. Play the FairPlay content offline.

>[!NOTE]
>
>FairPlay Streaming on the client does not start decryption if the persisted content key has expired. However, it will continue the user experience if the content key expires during playback. 
>
>See [Working with HTTP Live Streaming](https://developer.apple.com/library/content/documentation/AudioVideo/Conceptual/MediaPlaybackGuide/Contents/Resources/en.lproj/HTTPLiveStreaming/HTTPLiveStreaming.html#//apple_ref/doc/uid/TP40016757-CH11-SW3) document for more details.

## FairPlay license rotation {#section_D32AA08C61474B4F876AC2A5F18CB879}

License rotation is a scheme for preventing license hacking of content that plays for a long time.

In an M3U8 manifest, each key tag will apply to the following TS segments until the next key tag, or until the end of the file.

To add license rotation, do the following:

* Insert a new FairPlay key tag during license rotation time.

  Any number of key tags can be added.

  For linear contents, make sure to maintain the most recent key tag in the M3U8 window. iOS will request the next M3U8 when there are about two TS segments left to be played (around 20 seconds). If the new M3U8 contains new key tags, all of the key requests will happen immediately. The previous existing keys will not be requested again. iOS will wait for all of the key requests to finish before playback will start.

  For VOD contents with license rotation, all of the key requests will happen at the beginning of playback.

  Following is a sample M3U8 with key rotation:

