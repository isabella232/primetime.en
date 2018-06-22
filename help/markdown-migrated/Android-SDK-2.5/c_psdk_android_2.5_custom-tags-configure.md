---
description: Media streams can carry additional metadata in the form of tags in the playlist/manifest file, and this file indicates the placement of advertising. You can specify custom tag names and be notified when certain tags appear in the manifest file.
seo-description: Media streams can carry additional metadata in the form of tags in the playlist/manifest file, and this file indicates the placement of advertising. You can specify custom tag names and be notified when certain tags appear in the manifest file.
seo-title: Custom tags
title: Custom tags
---

# Custom tags

## HLS content tags {#section_E99299152089418FBA56F5F09FC547B0}

>[!IMPORTANT]
>
>This feature is not available for Safari on Apple computers, because uses the video tag, rather than Flash or MSE, to play HLS content.
provides out-of-the-box support for specific `codeph #EXT` advertising tags. Your application can use custom tags to enhance the advertising workflow or to support blackout scenarios. To support advanced workflows,  allows you to specify and subscribe to additional tags in the manifest. You can be notified when these tags appear in the manifest file.

>[!TIP]
>
>You can subscribe to custom tags both for VOD and live/linear streams.
>[!NOTE] {type="other" othertype="Limitation"}
>
>When HLS is played by using the Video tag in Safari, and not by using Flash Fallback, this feature will not be available in Safari.
## Using custom HLS tags {#section_AD032318AEF5418393D2B1DF36B0BABB}

Here is an example of a customized VOD asset:

```
#EXTM3U
#EXT-X-VERSION:3
#EXT-X-TARGETDURATION:7
 
#EXT-X-ASSET:AID=10
 
#EXTINF:9.9766,
seg1.ts
 
#EXTINF:9.9766,
seg2.ts
 
#EXTINF:9.9766,
seg3.ts
 
#EXT-X-AD:DURATION=10
#EXTINF:9.9766,
seg4.ts
 
#EXTINF:9.9766,
seg5.ts
 
#EXT-X-ENDLIST
```
Your application can set up the following scenarios:

* A notification when `codeph #EXT-X-ASSET` tags, or any other set of custom tag names to which you have subscribed, exist in the file.
* Insert ads when an `codeph #EXT-X-AD` tag, or any other custom tag name, is found in the stream.
You can subscribe to any of the following tags as custom tags:
* `codeph EXT-PROGRAM-DATE-TIME`
* `codeph EXT-X-START`
* `codeph EXT-X-AD`
* `codeph EXT-X-CUE`
* `codeph EXT-X-ENDLIST`
You will be notified with a`codeph TimedMetadata` event during the parsing of manifest files.

There are some advertising tags, such as `codeph EXT-X-CUE`, to which you are already subscribed. These ad tags are also used by the default opportunity generator. You can specify which ad tags are used by the default opportunity generator by setting the `codeph adTags` property.

