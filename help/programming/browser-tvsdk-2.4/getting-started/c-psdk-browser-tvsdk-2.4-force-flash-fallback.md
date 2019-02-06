---
description: The forceflash flag in the source list forces Flash fallback for a URL. For this URL, you can use Adobe Flash Player to play the content.
seo-description: The forceflash flag in the source list forces Flash fallback for a URL. For this URL, you can use Adobe Flash Player to play the content.
seo-title: Forcing the Flash fallback using the media source list
title: Forcing the Flash fallback using the media source list
uuid: 04b09734-15f7-4e7e-8802-344f550f9b05
---

# Forcing the Flash fallback using the media source list{#forcing-the-flash-fallback-using-the-media-source-list}

The forceflash flag in the source list forces Flash fallback for a URL. For this URL, you can use Adobe Flash Player to play the content.

In the media source list (for example in the `sources.js` file), you can set `forceflash` to `true`. For example: 

```js
{ 
        "title":"Title of the item listed in the media source list",
        "description":"Description of the item listed in the media source list",
        "isLive":true,
        "content":[ 
            { 
                "format":"HLS",
                "url":"https://path_to_HLS_stream.m3u8"
            },
 
        ],
        "forceflash" : true
},
```

