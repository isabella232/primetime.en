---
description: We use both the Bento4 packager and the Adobe offline packager to author encrypted DASH content. Bento4 takes as input unencrypted mp4 content.
seo-description: We use both the Bento4 packager and the Adobe offline packager to author encrypted DASH content. Bento4 takes as input unencrypted mp4 content.
seo-title: Package your content with Bento4
title: Package your content with Bento4
uuid: f9be32f5-26cc-472d-a2a2-f3a0d93a07e1
index: y
internal: n
snippet: y
---

# Package your content with Bento4{#package-your-content-with-bento}

We use both the Bento4 packager and the Adobe offline packager to author encrypted DASH content. Bento4 takes as input unencrypted mp4 content.

The Bento4 packager expects the input mp4 to be pre-fragmented. The Bento4 packager distribution includes a tool for this. 

1. **Calling Bento4**

       Typical Bento4 packager invocations would look like the examples below: 
       The example below combines PlayReady and Widevine schemes. In this particular case the packager is adding both Widevine content protection and PlayReady content protection initialization data to the output DASH content. 
       where

    * The value for the `--encryption-key` flag is in the form `<base16 encoded key id>:<base16 encoded encryption key>`. 
    
    * The `--widevine-header=provider:intertrust#content_id:2a` flag tells the packager to include the pssh box in the manifest, which TVSDK currently requires for playback. 
    * The value for `-playready-header` is for PlayReady license acqusition.

