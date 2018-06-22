---
description: To make closed captions available to your client player, you must enable them. The user can turn closed captions on or off and select the formatting.
seo-description: To make closed captions available to your client player, you must enable them. The user can turn closed captions on or off and select the formatting.
seo-title: Expose closed captions
title: Expose closed captions
---

# Expose closed captions

To expose closed captions:

>1. In `codeph PTMediaPlayer` object, set the `codeph closedCaptionDisplayEnabled` property.
>   If the user has enabled closed captions, this step displays the text.
>   >[!NOTE]
>   >
>   >The client user turns closed captioning on or off by using the iOS Accessibility Settings, and these settings also provide formattng options.
>   >[!NOTE]
>   >
>   >`codeph closedCaptionDisplayEnabled` property is deprecated. Use `codeph subtitlesOptions` property of `codeph PTMediaPlayerItem`. See [Expose subtitles](t_psdk_ios_1.4_subtitles-exposing-ios.md#t_psdk_ios_exposing-subtitles) to use closed captions.
>   
>   
>   
