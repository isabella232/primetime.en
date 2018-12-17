---
description: null
keywords: setSecure;VideoEngineView
seo-description: null
seo-title: Enable screen capture
title: Enable screen capture
uuid: 63c7b5a6-9e02-4c38-8592-a50f0f0fdf56
index: y
internal: n
snippet: y
---

# Enable screen capture{#enable-screen-capture}

 TVSDK disallows screen capture by default. The player calls `setSecure(true)` on the `com.adobe.ave.VideoEngineView` object at construction time. You have access to this object, as you have to construct a `VideoEngineView` object and supply it to the `VideoEngine` object.

To enable screen capture in your app: 

1. Construct the `com.adobe.ave.VideoEngineView` object.
1. Call `setSecure(false)` on your `VideoEngineView` object.
