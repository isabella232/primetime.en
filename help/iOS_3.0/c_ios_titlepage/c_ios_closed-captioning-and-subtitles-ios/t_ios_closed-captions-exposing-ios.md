---
description: To make closed captions available to your client player, you must enable them. The user can turn closed captions on or off and select the formatting.
seo-description: To make closed captions available to your client player, you must enable them. The user can turn closed captions on or off and select the formatting.
seo-title: Expose closed captions
title: Expose closed captions
uuid: ee044c1b-121a-4a6f-9899-8ee7e42277b4
index: y
internal: n
snippet: y
translate: y
---

# Expose closed captions

To make closed captions available to your client player, you must enable them. The user can turn closed captions on or off and select the formatting.

To expose closed captions: 

1. In `PTMediaPlayer` object, set the `closedCaptionDisplayEnabled` property.

   If the user has enabled closed captions, this step displays the text.
   >[!NOTE]
   >
   >The client user turns closed captioning on or off by using the iOS Accessibility Settings, and these settings also provide formattng options.

   >[!NOTE]
   >
   >`closedCaptionDisplayEnabled` property is deprecated. Use `subtitlesOptions` property of `PTMediaPlayerItem`. See [Expose subtitles](t_psdk_ios_1.4_subtitles-exposing-ios.md#t_psdk_ios_exposing-subtitles) to use closed captions. 

