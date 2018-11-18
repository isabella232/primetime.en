---
description: Use the helper class AuditudeSettings , which extends the MetadataNode class, to set up Adobe Primetime ad decisioning metadata.
seo-description: Use the helper class AuditudeSettings , which extends the MetadataNode class, to set up Adobe Primetime ad decisioning metadata.
seo-title: Set up ad insertion metadata
title: Set up ad insertion metadata
uuid: 8c9c4005-218a-4688-b72d-ea64fd89e9be
index: y
internal: n
snippet: y
---

# Set up ad insertion metadata{#set-up-ad-insertion-metadata}

Use the helper class AuditudeSettings , which extends the MetadataNode class, to set up Adobe Primetime ad decisioning metadata.

>[!TIP]
>
>Adobe Primetime ad decisioning was previously known as Auditude.

Advertising metadata is in the `MediaResource.metadata` property. When starting the playback of a new video, your application is responsible for setting the correct advertising metadata. 

1. Build the `AuditudeSettings` instance.

   ```
   var auditudeSettings:AuditudeSettings = new AuditudeSettings();
   ```

1. Set the Adobe Primetime ad decisioning mediaID, zoneID, domain, and the optional targeting parameters.

   ```
   auditudeSettings.zoneId = "yourZoneID"; 
   auditudeSettings.mediaId = "media_identifier"; 
   auditudeSettings.domain = "yourAuditudeDomain"; 
   var targetingInfo:Metadata = new Metadata(); 
   targetingInfo.setValue("yourParamName", "yourParamValue"); 
   auditudeSettings.targetingInfo = targetingInfo;
   ```

   >[!TIP]
   >
   >The media ID is consumed by TVSDK as a string, that is converted to an md5 value, and is used for the `u` value in the Primetime ad decisioning URL request. For example: 
   >
   >
   >` http://ad.auditude.com/adserver? **u**=c76d04ee31c91c4ce5c8cee41006c97d &z=114100&l=20150206141527&of=1.4&tm=15&g=1000002`

1. Create a `MediaResource` instance by using the media stream URL and the previously created advertising metadata.

   ```
   var mediaResourceMetadata:MetadataNode = new MetadataNode(); 
   mediaResourceMetadata.setNode(DefaultMetadataKeys.AUDITUDE_METADATA_KEY, auditudeSettings); 
   var mediaResource:MediaResource = new MediaResource( 
         "www.example.com/video/test.m3u8", 
         MediaResourceType.HLS,  
         mediaResourceMetadata);
   ```

1. Load the `MediaResource` object through the `MediaPlayer.replaceCurrentResource` method.

   The `MediaPlayer` starts loading and processing the media stream manifest. 

1. (Optional) Query the `MediaPlayerItem` instance to see whether the stream is live, regardless of whether it has alternate audio tracks, or whether the stream is protected.

   This information can help you prepare the UI for the playback. For example, if you know there are two audio tracks, you can include a UI control that toggles between these tracks. 

1. Call `MediaPlayer.prepareToPlay` to start the advertising workflow.

   After the ads have been resolved and placed on the timeline, the `MediaPlayer` transitions to the PREPARED state.
1. Call `MediaPlayer.play` to start the playback.
>TVSDK now includes ads when your media plays. 
