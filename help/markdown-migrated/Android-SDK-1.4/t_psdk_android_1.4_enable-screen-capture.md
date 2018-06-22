---
description: 
keywords: setSecure;VideoEngineView
seo-description: 
seo-title: Enable screen capture
title: Enable screen capture
---

# Enable screen capture

disallows screen capture by default. The player calls `codeph setSecure(true)` on the `codeph com.adobe.ave.VideoEngineView` object at construction time. You have access to this object, as you have to construct a `codeph VideoEngineView` object and supply it to the `codeph VideoEngine` object.

To enable screen capture in your app:

>1. Construct the `codeph com.adobe.ave.VideoEngineView` object.
>   
>1. Call `codeph setSecure(false)` on your `codeph VideoEngineView` object.
>   
>   
