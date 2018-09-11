---
description: If pttrackingmode=simple or ptplayer=ios-mobileweb, the manifest server sends back a JSON-formatted file containing Master-M3U8, a URL for the client to use to request the M3U8 file describing the content.
seo-description: If pttrackingmode=simple or ptplayer=ios-mobileweb, the manifest server sends back a JSON-formatted file containing Master-M3U8, a URL for the client to use to request the M3U8 file describing the content.
seo-title: JSON format for URL for requesting variant manifest playlist
title: JSON format for URL for requesting variant manifest playlist
uuid: 72616353-5a1a-461b-93e8-f765f5db5afa
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
