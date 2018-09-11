---
description: If pttrackingmode=simple or ptplayer=ios-mobileweb, the manifest server sends back a JSON-formatted file containing Master-M3U8, a URL for the client to use to request the M3U8 file describing the content.
seo-description: If pttrackingmode=simple or ptplayer=ios-mobileweb, the manifest server sends back a JSON-formatted file containing Master-M3U8, a URL for the client to use to request the M3U8 file describing the content.
seo-title: JSON format for URL for requesting variant manifest playlist
title: JSON format for URL for requesting variant manifest playlist
uuid: b9c711a1-788b-49a6-a880-4a2717486f13
index: y
internal: n
snippet: y
translate: y
---

# JSON format for URL for requesting variant manifest playlist

If pttrackingmode=simple or ptplayer=ios-mobileweb, the manifest server sends back a JSON-formatted file containing Master-M3U8, a URL for the client to use to request the M3U8 file describing the content.


<a id="json_variant"></a>

This is the format of the JSON file containing the `Master-M3U8` URL. 

```
{
"Master-M3U8": "http://manifest.auditude.com/auditude/variant/{publisherAssetID}/
  {sessionId}/{Base 64 of the url of the content}.m3u8
  ?u={Ad Request Id}
  &z={Ad Zone Id}
  &pttrackingmode=simple
  &pttrackingversion=v1
  &{other query parameters}"
}
```
