---
description: null
keywords: setSecure;VideoEngineView
seo-description: null
seo-title: Enable screen capture
title: Enable screen capture
uuid: 89d3ea7d-1342-430c-acf4-4ff6815f1af0
index: n
internal: n
snippet: y
translate: y
---

# Enable screen capture

 <!-- PH element: phrases/primetime-sdk-name --> disallows screen capture by default. The player calls `setSecure(true)` on the `com.adobe.ave.VideoEngineView` object at construction time. You have access to this object, as you have to construct a `VideoEngineView` object and supply it to the `VideoEngine` object. 
To enable screen capture in your app:

>1. Construct the `com.adobe.ave.VideoEngineView` object.
>1. Call `setSecure(false)` on your `VideoEngineView` object.
