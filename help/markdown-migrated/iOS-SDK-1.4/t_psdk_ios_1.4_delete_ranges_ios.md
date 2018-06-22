---
description: 
seo-description: 
seo-title: Delete Ranges
title: Delete Ranges
---

# Delete Ranges

To implement the`codeph  PTTimeRangeCollection` and delete ranges of content as ads:
>1. Prepare the `codeph  PTTimeRangeCollection`.
>   
>1. Set the type of the `codeph  PTTimeRangeCollection` to `codeph  PTTimeRangeCollectionTypeDeleteRanges`, which notifies  that the provided ranges need to be deleted.
>   ```
>   #define PSDK_TIMESCALE 100000 
>         
>   NSArray *ranges =  @[ 
>    [PTReplacementRange replacementRangeWithRange:CMTimeRangeMake(CMTimeMakeWithSeconds 
>    (0, PSDK_TIMESCALE),CMTimeMakeWithSeconds(60, AD_TIMESCALE))], 
>    [PTReplacementRange replacementRangeWithRange:CMTimeRangeMake(CMTimeMakeWithSeconds 
>    (120, PSDK_TIMESCALE),CMTimeMakeWithSeconds(60, AD_TIMESCALE))] 
>   ]; 
>         
>   PTTimeRangeCollection *timeRangeCollection = 
>    [[PTTimeRangeCollection alloc] initWithRanges:ranges 
>    type:PTTimeRangeCollectionTypeDeleteRanges];
>   ```
>   
>   
>1. Create the `codeph  PTAdMetadata` and set the `codeph  PTTimeRangeCollection`.
>   ```
>   //Create the PTPlayerItem metadata 
>   PTMetadata *metadata = [[PTMetadata alloc] init]; 
>     
>   //Create the Ad metadata 
>   PTAuditudeMetadata *adMetadata = [[PTAuditudeMetadata alloc] init]; 
>   adMetadata.timeRangeCollection = timerangeCollection; 
>   adMetadata.zoneId = adZoneId; 
>   adMetadata.domain = adDomain; 
>   adMetadata.signalingMode = PTAdSignalingModeServerMap; 
>     
>   //Set Ad metadata 
>   [metadata setMetadata:adMetadata forKey:PTAdResolvingMetadataKey]; 
>     
>   //Create PTMediaPlayerItem 
>   PTMediaPlayerItem *playerItem = [[[PTMediaPlayerItem alloc] initWithUrl:mediaUrl 
>                                                                   mediaId:mediaId 
>                                                                  metadata:metadata];
>   ```
>   >[!TIP]
>   >
>   >Ad insertion occurs after the deletion of the custom ranges based on the`codeph  PTAdMetadata` and the current `codeph  PTAdSignalingMode`.
>   
>   
>1. Create the player and start playback.
>   ```
>   //Create PTMediaPlayer using the created PTMediaPlayer 
>   PTMediaPlayer *player = [PTMediaPlayer playerWithMediaPlayerItem:playerItem]; 
>     
>   //Add player to the player UIView 
>   [self.playerView addSubview:(UIView *)player.view]; 
>     
>   //Start playback 
>   [player play];
>   ```
>   
>   
>   
