---
description: The Nielsen Analytics module requires a specific set of metadata configured for your implementation. Once the metadata is loaded, you attach the module to your MediaPlayer and communicate with it using APIs.
seo-description: The Nielsen Analytics module requires a specific set of metadata configured for your implementation. Once the metadata is loaded, you attach the module to your MediaPlayer and communicate with it using APIs.
seo-title: Integrate the Nielsen Analytics module
title: Integrate the Nielsen Analytics module
uuid: fb67817b-81a5-47bd-bc12-f802141f6254
index: n
internal: n
snippet: y
translate: y
---

# Integrate the Nielsen Analytics module

The Nielsen Tracker instance expects tracking metadata to be set through a ` TrackingMetadata` class. This example demonstrates the new and updated PDSK APIs described in "* APIs for Nielsen Analytics*") to set up the required metadata: 

>1. Create a Tracker Instance with every player item (values shown in the sample below are for demonstration purposes only).
>
>   ```
>   self.nielsenTracker = [[PTNielsenTracker alloc] initWithAppInfo:[self getNielsenAppInfo]]; 
>   [self.nielsenTracker attachMediaPlayer:self.player]; 
>     
>   - (NSDictionary *)getNielsenAppInfo { 
>     return @{ 
>       @"appid": @"C8CFD744-1C79-4F77-A014-B73B6552E37B", 
>       @"appversion": [PTSDK apiVersion], // this must be your specific app version 
>       @"appname": [[[NSBundle mainBundle] infoDictionary]  
>         objectForKey:@"CFBundleName"], // this must be your specific app name 
>       @"sfcode": @"aws", 
>       @"dma": @"123", 
>       @"ccode": @"456" 
>     }; 
>   }
>   ```
>
>1. Create a ` PTNielsenTrackingMetadata` instance.
>
>   ```
>   - (PTNielsenTrackingMetadata *)getNielsenTrackingMetadata 
>   { 
>       PTNielsenTrackingMetadata *metadata = [[[PTNielsenTrackingMetadata alloc] init] autorelease]; 
>        metadata.appInfo = @{ 
>            @"appid": @"C8CFD744-1C79-4F77-A014-B73B6552E37B", 
>            @"appversion": [PTSDK apiVersion], 
>            @"appname": [[[NSBundle mainBundle] infoDictionary] objectForKey:@"CFBundleName"], 
>            @"sfcode": @"aws", 
>            @"dma": @"123", 
>            @"ccode": @"456" 
>       }; 
>         
>       metadata.channelInfo = @{ 
>           @"channelName": [NSString stringWithString:_itemUrl], 
>           @"adModel": @"2", 
>           @"dataSrc": @"id3" 
>       }; 
>         
>       metadata.metadataInfo = @{ 
>           @"type": @"content", 
>           @"assetid": self.parent.adsTab.defaultMediaId, 
>           @"tv": @YES, 
>           @"program": @"MyProgram", 
>           @"title": @"MyEpisodeTitle", 
>           @"category": @"testcat", 
>           @"adModel": @"2", 
>           @"dataSrc": @"id3" 
>       }; 
>         
>       return metadata; 
>   } 
>   ```
>
>1. Add Nielsen Tracking Metadata to ` PTMetdata` instance.
>
>   ```
>   PTMetadata *metadata = [[PTMetadata alloc] init]; 
>   [metadata setMetadata:[self getNielsenTrackingMetadata] forKey:PTNielsenTrackingMetadataKey];
>   ```
>
