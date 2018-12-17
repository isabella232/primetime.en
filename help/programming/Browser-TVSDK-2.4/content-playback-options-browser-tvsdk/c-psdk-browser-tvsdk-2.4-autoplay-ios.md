---
description: null
seo-description: null
seo-title: Autoplay on iOS
title: Autoplay on iOS
uuid: f50d675a-d6c1-42b4-8d91-74a1f6abbe63
index: y
internal: n
snippet: y
---

# Autoplay on iOS{#autoplay-on-ios}

 The implementation of the volume API of AdobePSDK.MediaPlayer allows autoplaying content on devices running iOS version 10 or above. iOS allows autoplay only when the volume is muted. When the volume is set to zero, the API sets the `muted` property of the video tag to `true`, otherwise the `muted` property is set to `false`. The `play` API starts the playback without any user interaction or user gesture.

For autoplay on iPhone, additionally set the `playsInline` property of the `video` tag to `true`. 

```
videoDiv.getElementsByTagName('video')[0].playsInline = true;
```

>[!NOTE]
>
>Use of `playsInline` property starts the playback without the fullscreen mode.

