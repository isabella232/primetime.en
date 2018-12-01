---
description: To make closed captions available to your client player, you must enable them. The user can turn closed captions on or off and select the formatting.
seo-description: To make closed captions available to your client player, you must enable them. The user can turn closed captions on or off and select the formatting.
seo-title: Expose closed captions
title: Expose closed captions
uuid: 2c3e2d86-6b15-4670-bc4d-1594e1956dbd
index: y
internal: n
snippet: y
---

# Expose closed captions{#expose-closed-captions}

To make closed captions available to your client player, you must enable them. The user can turn closed captions on or off and select the formatting.

To expose closed captions: 

1. In `PTMediaPlayer` object, set the `closedCaptionDisplayEnabled` property.

   If the user has enabled closed captions, this step displays the text. 

   >[!NOTE]
   >
   >The client user turns closed captioning on or off by using the iOS Accessibility Settings, and these settings also provide formattng options.

   >[!NOTE]
   >
   >`closedCaptionDisplayEnabled` property is deprecated. Use `subtitlesOptions` property of `PTMediaPlayerItem`. See [Expose subtitles](../../c-psdk-ios-1.4-titlepage/c-psdk-ios-1.4-closed-captioning-and-subtitles-ios/t-psdk-ios-1.4-subtitles-exposing-ios.md#t_psdk_ios_exposing-subtitles) to use closed captions.

